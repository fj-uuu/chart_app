ディレクトリの構成とそれぞれの役割

* shims-tsx.d.ts/shims-vue.d.ts
TSの特有ファイル
vue.jsをTSで使えるようにする

* main.ts
new Vueのエントリーポイント
global設定書き込み

* App.vue
コンポーネントのルート
グローバルで使うCSS、コンポーネントで先にやりたい初期化処理を書く。

* views/
各ページのTOPの親コンポーネントを置く。
子コンポーネントとvuexの橋渡し役

* components/
ボタン、画像、ヘッダー、フッターなど部品コンポーネントをおく。
極力データを表示するだけのコンポーネントにしたい気持ち。

* store/
vuexを中心にアプリとstatsとそれを変更するmutation, veiwsとやり取りするactionを定義する。
アプリのロジックを詰める場所
mutationはprivateメソッドとして定義し、publicなのはactionとget propertyだけにする。

## Vuexが大事
* Action: UIから呼ばれる/APIを呼ぶ/mutationを呼ぶ
* mutation: stateを更新する
* getter: stateをごにょごにょしてUIに返す
という役割をそれぞれ担うように気をつけるだけ。
