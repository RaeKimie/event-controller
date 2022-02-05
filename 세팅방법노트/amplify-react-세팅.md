## Amplify와 React 앱 세팅하기
1. AWS amplify CLI 다운로드 `npm i -g @aws-amplify/cli`
2. React app 만들기 `npx create-react-app <app-name>`
3. Amplify CLI를 사용해 유저 프로필 만들기 `amplify configure`
    - 유저를 만들 수 있는 어드민으로 로그인할것
    - 배포할 리전 선택
    - IAM 유저 이름 설정 (콘솔 열림)
    - Access key와 secret 입력
    - 프로필 이름 설정
4. amplify 초기 설정 `amplify init`

## 가입과 로그인 기능 React앱에 추가하기
1. 리액트 엡에 authentication 추가 `amplify add auth`
2. `amplify push`
3. aws-exports.js 파일 확인시 추가된걸 확인할 수 있음.
4. `npm install aws-amplify @aws-amplify/ui-react`
5. App.js 다음과 같이 추가해줄것

[Amplify ui 문서](https://ui.docs.amplify.aws/getting-started/installation)

```
import './App.css';

import { Authenticator } from '@aws-amplify/ui-react';
import '@aws-amplify/ui-react/styles.css';

function App() {
  return (
    <div className="App">
      <header className="App-header">
       
        <Authenticator>
        {({ signOut, user }) => (
          <div className="App">
            <p>
              Hey {user.username}, welcome to my channel, with auth!
            </p>
            <button onClick={signOut}>Sign out</button>
          </div>
        )}
        </Authenticator>

        <h2>Hi</h2>
      </header>
    </div>
  );
}

export default App;

```
6. `npm start` 앱에서 로그인과, 회원가입, 비번찾기 추가된걸 확인할 수 있음

![alt text](https://github.com/RaeKimie/event-controller/blob/master/screenshots/login.jpg?raw=true)

