# Laporan Proyek Machine Learning - Nur Baiti Nasution
## _**Students Performance Based On Family Background**_

[![N|Solid](https://w7.pngwing.com/pngs/135/11/png-transparent-student-education-graduation-ceremony-icon-school-elements-child-class-public-relations.png)](https://w7.pngwing.com/pngs/135/11/png-transparent-student-education-graduation-ceremony-icon-school-elements-child-class-public-relations.png)

### Domain Proyek
Seringkali kita berpendapat bahwa kesempatan siswa sekolah untuk berprestasi sangat dipengaruhi oleh latar belakang keluarganya. Latar belakang yang dimaksud adalah tingkat pendidikan orang tua, tingkat penghasilan orang tua, asal suku, dan sebagainya. Hal ini telah ditunjukkan oleh beberapa studi yang menunjukkan bahwa latar belakang keluarga memang berpengaruh terhadap hasil belajar siswa di sekolah. Salah satunya adalah studi yang dilakukan oleh AJ Egalite dalam artikelnya yang berjudul ["How Family Background Influences Student Achievement"](https://www.uccronline.it/wp-content/uploads/2012/06/201604educationnext.pdf).
Berangkat dari hal tersebut, proyek ini bertujuan untuk mengembangkan model machine learning yang dapat memprediksi nilai akhir siswa dan masa studinya berdasarkan data latar belakang keluarganya. Mengapa model ini perlu dibuat? Agar pihak sekolah atau orang tua dapat memperoleh gambaran mengenai nilai akhir siswa dan dapat memberikan tindakan preventif jika nilai jelek yang muncul. Tindakan preventif dapat berupa tambahan jam pelajaran dari sekolah atau pemberian tutor sebaya untuk siswa yang berisiko memperoleh nilai buruk. 

### Business Understanding 
Dari uraian pada bagian sebelumnya, dapat dirumuskan permasalahan yang akan diselesaikan yaitu 
- Bagaimana model machine learning yang dapat melakukan prediksi nilai akhir mahasiswa berdasarkan data latar belakang orang tua?
- Bagaimana model machine learning yang dapat melakukan prediksi masa studi mahasiswa berdasarkan data latar belakang orang tua?

Dengan demikian, tujuan dari proyek ini adalah 
- untuk mengembangkan model machine learning yang dapat melakukan prediksi nilai akhir mahasiswa berdasarkan latar belakang orang tua. 
- untuk mengembangkan model machine learning yang dapat melakukan prediksi masa studi mahasiswa berdasarkan latar belakang orang tua

#### Solution Statement
Untuk dapat mencapai tujuan di atas, kita dapat: 
- Menggunakan algoritma klasifikasi untuk mengembangkan model, kemudian melakukan hyperparameter tuning untuk mencari model terbaik. Penentuan model terbaik menggunakan akurasi. Jika akurasi mencapai lebih dari 0.75 maka model dianggap cukup baik.
- Menggunakan algoritma regresi dan menggunakan nilai R square sebagai ukuran keberhasilannya. Jika R square > 0.75, maka model dianggap cukup baik. 

### Data Understanding
Data yang digunakan pada proyek ini adalah data graduation rate dari blog [Royce Kimmons](http://roycekimmons.com/tools/generated_data/graduation_rate). Dalam data tersebut terdapat 7 buah atribut yaitu 
- Atribut ACT composite score, yaitu merupakan rata-rata dari 4 tes utama yaitu English, Reading, Math, and Science, yaitu merupakan nilai ujian untuk mengukur kemampuan berpikir matematis dan menalar. 
- Parental level of education, yaitu tingkat pendidikan orang tua
- Parental income, yaitu penghasilan orang tua dalam US dollar
- High school gpa, yaitu nilai akhir ketika SMA
- College gpa, yaitu IPK terakhir
- Years to graduate, yaitu masa studi dalam satuan tahun

__Visualisasi Data Setiap Atribut__
Berikut adalah visualisasi data untuk masing-masing atribut yang digunakan. 


Markdown is a lightweight markup language based on the formatting conventions
that people naturally use in email.
As [John Gruber] writes on the [Markdown site][df1]

> The overriding design goal for Markdown's
> formatting syntax is to make it as readable
> as possible. The idea is that a
> Markdown-formatted document should be
> publishable as-is, as plain text, without
> looking like it's been marked up with tags
> or formatting instructions.

This text you see here is *actually- written in Markdown! To get a feel
for Markdown's syntax, type some text into the left window and
watch the results in the right.

## Tech

Dillinger uses a number of open source projects to work properly:

- [AngularJS] - HTML enhanced for web apps!
- [Ace Editor] - awesome web-based text editor
- [markdown-it] - Markdown parser done right. Fast and easy to extend.
- [Twitter Bootstrap] - great UI boilerplate for modern web apps
- [node.js] - evented I/O for the backend
- [Express] - fast node.js network app framework [@tjholowaychuk]
- [Gulp] - the streaming build system
- [Breakdance](https://breakdance.github.io/breakdance/) - HTML
to Markdown converter
- [jQuery] - duh

And of course Dillinger itself is open source with a [public repository][dill]
 on GitHub.

## Installation

Dillinger requires [Node.js](https://nodejs.org/) v10+ to run.

Install the dependencies and devDependencies and start the server.

```sh
cd dillinger
npm i
node app
```

For production environments...

```sh
npm install --production
NODE_ENV=production node app
```

## Plugins

Dillinger is currently extended with the following plugins.
Instructions on how to use them in your own application are linked below.

| Plugin | README |
| ------ | ------ |
| Dropbox | [plugins/dropbox/README.md][PlDb] |
| GitHub | [plugins/github/README.md][PlGh] |
| Google Drive | [plugins/googledrive/README.md][PlGd] |
| OneDrive | [plugins/onedrive/README.md][PlOd] |
| Medium | [plugins/medium/README.md][PlMe] |
| Google Analytics | [plugins/googleanalytics/README.md][PlGa] |

## Development

Want to contribute? Great!

Dillinger uses Gulp + Webpack for fast developing.
Make a change in your file and instantaneously see your updates!

Open your favorite Terminal and run these commands.

First Tab:

```sh
node app
```

Second Tab:

```sh
gulp watch
```

(optional) Third:

```sh
karma test
```

#### Building for source

For production release:

```sh
gulp build --prod
```

Generating pre-built zip archives for distribution:

```sh
gulp build dist --prod
```

## Docker

Dillinger is very easy to install and deploy in a Docker container.

By default, the Docker will expose port 8080, so change this within the
Dockerfile if necessary. When ready, simply use the Dockerfile to
build the image.

```sh
cd dillinger
docker build -t <youruser>/dillinger:${package.json.version} .
```

This will create the dillinger image and pull in the necessary dependencies.
Be sure to swap out `${package.json.version}` with the actual
version of Dillinger.

Once done, run the Docker image and map the port to whatever you wish on
your host. In this example, we simply map port 8000 of the host to
port 8080 of the Docker (or whatever port was exposed in the Dockerfile):

```sh
docker run -d -p 8000:8080 --restart=always --cap-add=SYS_ADMIN --name=dillinger <youruser>/dillinger:${package.json.version}
```

> Note: `--capt-add=SYS-ADMIN` is required for PDF rendering.

Verify the deployment by navigating to your server address in
your preferred browser.

```sh
127.0.0.1:8000
```

## License

MIT

**Free Software, Hell Yeah!**

[//]: # (These are reference links used in the body of this note and get stripped out when the markdown processor does its job. There is no need to format nicely because it shouldn't be seen. Thanks SO - http://stackoverflow.com/questions/4823468/store-comments-in-markdown-syntax)

   [dill]: <https://github.com/joemccann/dillinger>
   [git-repo-url]: <https://github.com/joemccann/dillinger.git>
   [john gruber]: <http://daringfireball.net>
   [df1]: <http://daringfireball.net/projects/markdown/>
   [markdown-it]: <https://github.com/markdown-it/markdown-it>
   [Ace Editor]: <http://ace.ajax.org>
   [node.js]: <http://nodejs.org>
   [Twitter Bootstrap]: <http://twitter.github.com/bootstrap/>
   [jQuery]: <http://jquery.com>
   [@tjholowaychuk]: <http://twitter.com/tjholowaychuk>
   [express]: <http://expressjs.com>
   [AngularJS]: <http://angularjs.org>
   [Gulp]: <http://gulpjs.com>

   [PlDb]: <https://github.com/joemccann/dillinger/tree/master/plugins/dropbox/README.md>
   [PlGh]: <https://github.com/joemccann/dillinger/tree/master/plugins/github/README.md>
   [PlGd]: <https://github.com/joemccann/dillinger/tree/master/plugins/googledrive/README.md>
   [PlOd]: <https://github.com/joemccann/dillinger/tree/master/plugins/onedrive/README.md>
   [PlMe]: <https://github.com/joemccann/dillinger/tree/master/plugins/medium/README.md>
   [PlGa]: <https://github.com/RahulHP/dillinger/blob/master/plugins/googleanalytics/README.md>
