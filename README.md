# Compilation Context


## compileOnSave
- true / false(default)
- 파일을 save하면 자동으로 compile하겠다.
- vs 2015 with typescript 1.8.4 이상 또는 atom-typescript 플러그인을 쓰면 적용 가능하다.

## extends
- string(상속을 받아올 부모 설정의 path)
- 설정을 상속할 때 사용한다.
- 외부설정 가져오기 <br/>
 ```npm install --save-dev @tsconfig/deno```

## files
- 상대 혹은 절대 경로의 list 배열.
- exclude, include 보다 쎄다.
- files, exlude, include 설정이 없으면 전부 다 컴파일 하려 한다.

## include
- *을 사용하면, ```.ts, .tsx, .d.ts```만 포함한다.
  - .js 를 포함하려면 allowJS 설정을 추가한다.
- exclude 보다 약하다.
- glob 패턴(.gitignore같은)

## exclude
- 설정을 안하면 4가지 (node_modules, bower_components, jspm_packages, <outDir>)를 defualt로 제외한다.
- <outDir> 은 항상 제외한다. (include에 있어도.)
- glob 패턴


## @types
- 아무 설정을 안하면 node_modules/@types에서 모든 경로를 찾아서 사용한다.
- typeRoots
  - 배열 안에 들어있는 경로들 아래서만 가져온다.
- types
  - 배열 안의 모듈 혹은 ./node_modules/@types/ 안의 모듈 **이름**에서 찾아온다.
  - 빈 배열([])을 넣으면 이 시스템을 이용하지 않겠다는 뜻이다.
- typeRoots와 types는 같이 사용하지 않는다.


## target
- 빌드의 결과물을 어떤 버전으로 할 것인지 결정한다.
- default: ES3


## lib
- 기본 type definition 라이브러리를 어떤 것을 사용할 것인지 결정한다.
- lib를 지정하지 않았을 때, target이
  - ES3 이면, lib.d.ts
  - ES5 이면, dom, es5, scripthost
  - ES6 이면, dom, es6, dom.iterable, scripthost
- lib를 지정하면 그 lib 배열로만 라이브러리를 사용한다.
  - 빈 배열([])이면 'no definition found ........' 에러가 뜰 것 이다.


## outDir, outFile, rootDir
- outFile: 모든 ts파일의 컴파일 결과를 여기에 지정한 하나의 파일로 생성한다.
- outDir: 컴파일된 **js파일**이 저장될 경로가 된다.
- rootDir: **ts파일**이 존재할 폴더를 지정한다.
  - 지정한 폴더에 존재하지 않는 ts파일이 있을 시 에러.


## strict
- 무조건 true로 설정하는게 기본.

옵션 | 설명
--|--
--noImplicitAny | any타입이라고 명시하지 않았을 때, any로 추론되면 직접 any로 지정해야 한다.
--noImplicitThis | this에 어떤 형태가 들어올 수 있는지 제한한다. (any로 지정하는 것이 합리적이다.)
--strictNullChecks | 모든 타입에 null이나 undefined가 들어가지 않게 제한한다. (예외적으로, void는 undefined를 가질 수 있다.)
--strictFunctionTypes | 함수 타임에 대한 bivariant 매개변수 검사를 비활성한다.(...?)
--strictPropertyInitialization | 클래스의 속성이 생성자에서 초기화 되었는지 확인한다.
--stictBindCallApply | bind, call, apply를 사용할 때 엄격하게 체크하도록 한다.(...?)
--alwaysStrict | js를 strict mode로 분석하고 컴파일된 js파일에 "use strict"를 추가한다.



