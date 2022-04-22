v# 프로젝트 명 : mano-NFT

## 프로젝트 목표 : NFT 발행 및 간단한 Dapp 만들기

## 프로젝트 기간 : 2022.03-28 ~ 2022.04.17

# 목차

1. 개요
2. 목적
3. 사용기술
4. 주요기능
5. 발생이슈 & 해결과정

# 1. 개요

NFT 발행 및 간단한 Dapp 만들기

# 2. 목적

> 1. 오픈제플린 라이브러리를 사용하여 ERC-721 표준을 구현한 컨트랙트
> 2. 리액트 라이브러리를 활용한 프론트엔드 애플리케이션

# 4. 사용기술

- 컨트랙트: `Solidity`, `Hardhat`, `Openzeppelin`
- Wallet: `MetaMask`
- 테스트넷: `Rinkeby`
- 프레임워크 : `React`
- 웹 화면 구성 : `MUI`
- 개발 Tool : `Visual Studio Code`
- 프로젝트 관리 Tool : `GitHub`

사용 모듈 :

```
"canvas": "^2.8.0",
"nft.storage": "^4.0.1"

"@nomiclabs/hardhat-ethers": "2.0.0",
"@nomiclabs/hardhat-waffle": "2.0.0",
"@openzeppelin/contracts": "^4.3.3",
"chai": "4.2.0",
"ethereum-waffle": "3.0.0",
"ethers": "5.0.0",
"hardhat": "2.6.8",
"hardhat-deploy": "^0.9.10"

"@mui/material": "^5.1.1",
"opensea-js": "^1.2.7",

```

# 5. 주요기능

#### canvas

    -   이미지들을 조합하여 하나의 이미지 생성

#### nft.storage

    -   생성된 이미지를 IPFS에 업로드하고 메타정보 생성

#### Openzeppelin

    -   ERC-721 표준을 준수하는 스마트 컨트랙트 작성

#### React, MUI

    -   NFT 발행할 수 있는 애플리케이션

#### Opensea

    -   토큰 조회, 판매, 판매상태 조회

# 6. 발생이슈 & 해결 과정

### "컴포넌트에서 map() 메서드 사용"

[상황] ![다운로드](https://user-images.githubusercontent.com/98136297/164587281-1d615c4e-20f6-45b3-b152-82fe92c969be.png)

[문제] React v18에서 ReactDOM.render 미지원

[해결]
https://reactjs.org/link/switch-to-createroot

// Before
import { render } from 'react-dom';
const container = document.getElementById('app');
render(<App tab="home" />, container);

// After
import { createRoot } from 'react-dom/client';
const container = document.getElementById('app');
const root = createRoot(container); // createRoot(container!) if you use TypeScript
root.render(<App tab="home" />);
