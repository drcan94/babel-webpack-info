## BABEL NEDİR? 

### ES standartlarının yeni versiyonlarına göre yazılan kodların browserlar'ın çoğunluğunun desteklediği bir standarda (örneğin ES5) transpile eder.
### https://kangax.github.io/compat-table/es5/ adresinden browser uyumluluğu ES5 için incelenebilir.
### "npm init" komutu ile projeyi başlatıyoruz
### "npm i @babel/core @babel/polyfill @babel/preset-env @babel/cli --save-dev" ile de babel i development ortamımıza kuruyoruz.
### babel ı lokale kurduğumuz için cli da kullanmak için direkt "babel ..." şeklinde yazamayız. "./node_modules/.bin/babel src -d dist" yazarak babel i kullanabiliriz. Bunu package.json içine "scripts" alanında istediğimiz key (ben build olarak yapacağım)'in value'si olarak atayarak da uzun uzun yazmaktan kurtulabiliriz ve sadece "babel ..." ifadesi yeterli olur.
### öncelikle .babelrc isimli babel conf dosyasını oluşturmamız ve ilgili presetleri vermemiz gerekiyor
### sonra npm run build dediğimiz zaman dist klasöründe transpile edilen index.js dosyası oluşacaktır.

####

## WEBPACK NEDİR? BUNDLER'dır.
### Kod yazarken modüler olarak kullandığımız çok sayıda dosya ile çalışırız. Bu hem bağımlılık (dependency) sorunlarına hem de performans kayıplarına yol açtığı için webpack tool'u ile tek bir js (veya css...) dosyası oluşturarak uygulama yüklenme hızını artıyoruz. Aynı zamanda recursion konseptiyle dependency-graph'a otomatik olarak ekleyerek tüm statik dosyaları birbirine bundle eder (bağlar)

### Babel ile webpack arasında ilişki kurabilmek için "npm i babel-loader --save-dev" kurmamız gerekiyor
### Sonra "npm i webpack-cli webpack --save-dev" ile webpack'i kurmamız gerekiyor
### .babelrc dosyasına artık ihtiyaç yok çünkü webpack.config.js içinde zaten presetleri tanımlayacağız ve babel'ı kendi çalıştıracak zaten
### webpack çalıştırabilmek için yine script eklememiz gerekiyor
### "buildwp": "webpack --watch" şeklinde ekliyoruz
### ve "npm run buildwp" deyince build.js isimli dosyamız dist içinde oluşur.
### sonra index.html dosyasına dist/build.js'yi eklersek de en son oluşan tek js dosyasını eklemiş oluruz projemize