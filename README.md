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



