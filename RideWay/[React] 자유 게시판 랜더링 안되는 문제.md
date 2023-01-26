# 게시판 조회 문제

### 🧨 에러사항

- `freeBoards`의 데이터를 불러 올 대 `undefined` 에러가 발생하면서 홈페이지가 생성되지 않게 됨.
  - 3시간 이상 삼항 연산자, `&&`조건을 사용해봤지만 모두 헛수고였다.

### 😀 해결

- 코치님의 도움으로 `type`문제라는 것을 알게 되었다.
- 기존 `default`값은 `Array`여서 `length`가 적용되지만, `axios`로 불러오는 값은 `Object`타입을 가지고 있어서 `undefined` 반환이 발생한다. 즉 타입을 잘 맞춰줘야 해결할 수 있는 부분이었다. 역시 타입스크립트를 사용하는 이유가 있다.
- `state`의 기본값과 불러오는 값을 잘 확인할 수 있도록 하자.

```jsx
import React, { useEffect } from 'react';
import { useDispatch, useSelector } from 'react-redux';
// import FreeArticleListItem from './FreeArticleListItem';
import { LOAD_FREE_BOARD_REQUEST } from '../../store/modules/communityModule';
import FreeArticleListItem from './FreeArticleListItem';

const FreeArticleList = () => {
  const dispatch = useDispatch();
  useEffect(() => {
    dispatch({
      type: LOAD_FREE_BOARD_REQUEST,
      data: {
        page: 0,
      },
    });
  }, []);
  const { freeBoards } = useSelector(state => state.community);

  return (
    <div>
      {freeBoards.content && (
        <table>
          <thead>
            <tr>
              <th>번호</th>
              <th>제목</th>
              <th>작성일</th>
              <th>작성자</th>
              <th>조회수</th>
            </tr>
          </thead>
          <tbody>
            {freeBoards.content.map(board => (
              <FreeArticleListItem key={board.boardId} board={board} />
            ))}
          </tbody>
        </table>
      )}
    </div>
  );
};
export default FreeArticleList;
```

