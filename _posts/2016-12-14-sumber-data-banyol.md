---
layout: post
title: "sumber data banyol"
description: ""
date: 2016-12-14
tags: [nlp, search engine]
share: true
---

menulis mesin pencari yang menghasilkan hasil pencarian yang relevan membutuhkan sedikit kesabaran :). untuk menerapkan nlp pada mesin pencari, terlebih dahulu kita membangun sebuah web sederhana, dengan konsep yang sama seperti reddit.

import modul

```
from flask import (
    Flask,
    redirect,
    url_for,
    render_template,
    flash,
    request
)

from flask_sqlalchemy import SQLAlchemy
from flask.ext.sqlalchemy import SQLAlchemy
```

kemudian buat instance dari class Flask dan SQLAlchemy.

```
app = Flask(__name__)
app.secret_key = 'HollaASAhds()*)'
db = SQLAlchemy(app)
```

2 buah model, model Questions dan Comments.
dimana Questions berelasi one-to-many dengan Comments.

```
class Questions(db.Model):
    id = db.Column(db.Integer, primary_key=True)
    title = db.Column(db.Text(50))
    descr = db.Column(db.Text(50))
    questions = db.relationship('Comments', backref='questions', lazy="dynamic")

    def __repr__(self):
        return '<Questions {}>'.format(self.title)


class Comments(db.Model):
    id = db.Column(db.Integer, primary_key=True)
    text = db.Column(db.Text(50))
    questions_id = db.Column(db.Integer, db.ForeignKey('questions.id'))

    def __repr__(self):
        return '<Comments {}>'.format(self.text)
```

dimana tabel questions memiliki relasi dengan tabel comments (one to many) `questions --> comments`.

setelah model, selanjutnya saya telah membuat beberapa view.

view index
```
@app.route('/', methods=['GET'])
def index_page():
    return render_template('index.html', questions=Questions.query.order_by(Questions.id.desc()).all())
```

mengirim halaman index.html kemudian dengan data `questions`
dalam bentuk list, dalam hal ini Questions diurutkan dari id yang terbesar sampai yang terkecil. karena setiap ada pertanyaan baru yang masuk ke database, id dari questions akan increment +1.
