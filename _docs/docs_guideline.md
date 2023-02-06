---
title: 블로그 문서 작성 지침
last_modified_at: 2020-03-07
---

이 문서는 [**반야자비의 웹로그 저장소**](https://blog.banyazavi.com/){: target="_blank"}의 문서 작성을 위한 지침을 정리합니다.

---

[**Github Pages**](https://pages.github.com/){: target="_blank"}의 사이트 빌더인 [**Jekyll**](https://jekyllrb.com/){: target="_blank"}은 **Markdown**이라는 편집 문법을 차용하고 있습니다. 이와 같은 사이트 환경에 원활하게 대응하기 위해서는, 사이트를 구성하는 여러 요소에 대한 사용 방법을 명확하게 규정할 필요가 있습니다.

따라서 이 글에서는

- 블로그 문서 일관성 확보
- 문서 작성 시 문서 형식에 대한 부담 완화

를 위하여,

- 문서 메타데이터 정보
- Markdown 문법의 의미와 규칙, 용례
- 표준 문서 규격 및 작성 정책

을 정의합니다.

---

# 문서 메타데이터 정보

**문서 메타데이터 정보**란 깃허브 페이지의 지킬 사이트 빌더를 원활하게 사용하기 위해 추가되는 정보입니다.

## 파일명

**파일명**은 `_posts` 디렉토리에 기록되는 `.md` 확장자를 가진, 개별 문서의 실제 파일에 대한 이름입니다.

### 파일명 형식

```
YYYY-MM-DD-문서 제목.md
```

파일명은 띄어쓰기를 사용합니다. 파일명의 공백 처리에 대한 언더스코어 (`_`) 및 하이픈 (`-`) 은 허용하지 않습니다.

규칙 이외의 정보는 파일명에 추가되지 않습니다. 동일한 작성 일자와 동일한 문서 제목이 존재하는 경우에는 후행 문서가 다음날 작성된 것으로 간주합니다.

## 머릿말

**머릿말**은 마크다운 문서의 최상단에 위치하는 해당 문서에 대한 정보입니다.

### 머릿말 형식

```
---
title: title
excerpt: Post excerpt
[categories:
  - Category]
tags:
  - Tag 1
  - Tag 2
  - ...
---
```

- **title**은 문서의 제목입니다. 이 정보는 문서 목록에 노출되며, 파일명의 해당 요소와 동일해야 합니다.
- **excerpt**는 문서의 개요입니다. 이 정보는 문서 제목과 함께 노출되는 부분으로, 문서 내용에 대해 짧고 재미있게 요약한 내용을 담습니다. 한 문장일 필요는 없으나, 한 줄로 적어야 합니다.
- **categories**는 연재 문서의 주제 정보입니다. 이 정보가 존재할 경우 반드시 한 개만 등록해야 합니다.
- **tags**는 해당 문서에 대한 키워드의 목록입니다. 이 목록은 사전 순으로 정렬하여 등록해야 합니다.
- **categories**와 **tags**는 한글과 띄어쓰기를 허용합니다.

### 제목

문서의 **제목**은 해당 문서의 주제를 가장 잘 드러내는 구절 또는 문장입니다. 가능한 한 문장 이내로 표현하고, 마지막 문장의 마침표 (`.`) 는 생략합니다.

문서의 제목이 해당 문서의 파일명과 머릿말의 title로 사용되므로, 이 정보에에 사용 불가능한 값으로 제목을 작성할 수 없습니다 (e.g. 역슬래시 (`\`), 콜론 (`:`) 등). 부득이하게 이 값을 사용해야 하는 경우 동일 의미의 특수문자를 사용해야 합니다.

연재되는 문서의 경우, 카테고리명 (또는 카테고리명의 약칭) 을 대괄호 (`[]`) 로 감싸 제목의 말머리로 사용할 수 있습니다. 단, 이 말머리는 문서의 파일명에는 적용하지 않습니다.

### 카테고리

**카테고리**는 연재 문서의 주제 정보로써, **GNB**<sup>Global Navication Bar</sup>의 **카테고리** 항목에서의 문서 분류를 위한 값입니다.

이 정보는 문서의 소속으로써 기능하므로, 반드시 한 개의 카테고리만을 가져야 합니다. 연재되는 문서가 아닌 경우 카테고리 정보는 사용하지 않습니다. 작성 당시 연재 주제가 없던 문서가 후일 연재에 편입될 경우 카테고리 정보를 추가합니다.

### 태그

**태그**는 해당 문서에 대한 키워드의 목록으로써, GNB의 **태그** 항목에서의 문서 분류를 위한 값입니다. 이 정보는 여러 가지를 사용할 수 있습니다.

문서에 대한 태그로 해당 문서에서 다루는 주요 논제나 개념을 작성할 수 있습니다. 한국어와 영어 모두 사용이 가능하나, 같은 대상에 대해 두 가지 이상의 표현이 사용되었을 경우, 추후 블로그 정비 시 이를 가장 범용적으로 사용되는 표현 한 가지로 일치시켜야 합니다.

# Markdown 문법의 의미와 규칙, 용례

**Markdown**은 지킬 문서를 **HTML**<sup>HyperText Markup Language</sup>로 파싱하기 위한 편집 문법입니다.

이 문단에서는 각 마크다운 구문의 용도를 제한하여 일관성 있는 문서를 구성할 수 있도록 합니다.

## 제목 (Header)

### 제목 형식

```
# Header 1

## Header 1.1

### Header 1.1.1

## Header 1.2

# Header 2
```

이 구문은 문서 내 각 문단의 주제로써, 테마에 **TOC**<sup>Table of Contents</sup> 기능이 있을 경우, 해당 영역의 앵커로 사용되는 부분입니다.

문서의 제목과 마찬가지로, 각 문단의 주제를 가장 잘 드러내는 구절 또는 문장으로 작성하며, 가능한 한 문장 이내로 표현하고, 마지막 문장의 마침표 (`.`) 는 생략합니다.

제목 계층에 따라 해시태그 (`#`) 개수를 조절하여 표현하며, 스타일 요소에 따라 계층에 맞지 않는 해시태그 개수를 사용하는 것은 금지됩니다.

제목과 본문 사이에는 빈 줄을 하나 추가합니다.

특정 제목의 하위 제목에 대해 순서를 표시해야 할 경우 그 순서를 말머리로 하여 제목을 사용할 수 있습니다. 순서의 각 계층 구분은 온점 (`.`) 으로 합니다.

### e.g. 순서 표시가 필요한 경우

```
# 어떤 제목

...

# 하위에 순서 표시가 필요한 제목

## 1. 계층 1 제목

### 1.1 계층 1의 하위 1 제목

...

### 1.2 계층 1의 하위 2 제목

...

## 2. 계층 2 제목

...

# 다른 제목
```

## 강조 (Bold and Emphasize)

**강조** 문법으로는 **굵은 글씨** (`**Bold**`) 만 사용하며, *이탤릭체* (`*Italic Type*`) 는 사용하지 않습니다.

강조는 다음과 같은 상황에 사용합니다.

- 해당 문단의 핵심 키워드가 처음 사용되었을 경우
- 윗 첨자 (`<sup>Superscript</sup>`) 로 해설되는 약어의 표현
- 기타 해당 구문을 상기시켜야 할 경우

글 작성 시 강조 문법이 남용되지 않도록 주의해야 합니다.

## 취소선 (Strikethrough)

**취소선**은 문서의 주제와 관련이 적은 서술, 주로 농담에 사용됩니다. ~~넝담~ㅎ~~ 문법은 해당 구문의 앞뒤로 틸드 두 개 (`~~Strikethrough~~`) 를 사용합니다.

삭제나 수정된 내용은 취소선을 사용하여 표시하지 않고 문서를 개정하여 그 내용을 변경합니다. 변경 이전의 내용에 대한 서술이 필요할 경우 개정 전후의 내용에 대한 문단을 추가하거나 [NOTE]를 사용합니다.

즉, 취소선은 핵심 정보 전달과는 무관한 가벼운 상황에만 사용하는 것을 원칙으로 합니다. ~~그래야 나중에 취소선만 검색해서 부끄러운 드립들을 날려버릴 수 있거든~~

## 이미지 (Images)

### 이미지 형식

```
![이미지 설명]({{"/assets/images/YYYY-MM-DD/NO-ORD.ext"| relative_url}})[__
이미지 캡션]
```

문서에 사용되는 이미지는 `/assets/images` 경로 이하에 저장합니다. 하위 경로의 구성은 아래의 규칙으로 합니다.

1. **YYYY-MM-DD/**: 해당 문서의 작성일
1. **NO**: 동일 작성일 내 문서 작성 순서
1. **ORD**: 동일 문서 내 이미지 등장 순서 (2자리)
1. **.ext**: 이미지 파일의 확장자

참조 사이트와의 트래픽 문제를 방지하기 위하여 이미지는 가능한 사이트 내부에 두고 `relative_url` 옵션을 통해 상대경로 호출하여 사용합니다. 그러나 이미지에 대한 저작권 등이 우려되는 경우에는 해당 사이트의 주소를 사용하여 이미지를 삽입하거나, 링크 구문을 사용하여 이미지가 사용된 페이지를 직접 링크합니다.

웹 접근성을 위한 이미지 설명은 생략할 수 없습니다.

이미지에 대한 짧은 보충 설명이 필요할 경우, 강제 개행 (`  `: 띄어쓰기 두 칸) 하여 캡션과 같이 사용할 수 있습니다.

문서 개정으로 이미지가 추가/삭제될 경우 등장 순서 (ORD) 규정을 완화하여 적용할 수 있습니다. 그러나 추후 블로그 정비 시 다시 규정에 맞추어 파일명과 인용 구문을 바꿔야 합니다.

## 링크 (Links)

### 링크 형식

```
[링크할 구절](https://blog.banyazavi.com/){: target="_blank"}
```

타 사이트의 페이지를 링크하는 경우에는 반드시 **새 창에서 열기** 옵션 (`{: target="_blank"}`) 을 추가해야 합니다. 블로그 내 문서 이동의 경우 이 옵션을 생략할 수 있습니다.

블로그 내 문서 이동하는 경우 주소의 호스트를 제외한 경로만을 사용합니다. 단, 본 블로그를 타 사이트로 간주하는 경우에는 전체 주소를 사용할 수 있습니다. 그러나 이 경우에는 새 창에서 열기 옵션 또한 강제됩니다.

## 목록 (Lists)

### 목록 형식

```
- Unordered List a
- Unordered List b
- ...

1. Ordered List 1
1. Ordered List 2
1. ...
```

**순서가 없는 목록**과 **순서가 있는 목록**을 명확하게 구분하여 사용합니다. 항목 간 선후관계가 있거나 중요도 등의 순위를 매길 수 있는 경우에는 순서가 있는 목록을 사용합니다. 그 외의 경우에는 순서가 없는 목록을 사용합니다.

순서가 없는 목록의 문법은 하이픈 (`-`) 만을 사용합니다. 애스터리스크 (`*`) 는 강조 문법과의 혼동을 야기할 수 있어 사용하지 않습니다.

순서가 있는 목록의 문법은 `1.`만을 사용합니다. `2.` 이후의 순서에도 변함 없이 `1.`을 사용합니다. 특정 순서부터 시작하거나 순서를 건너뛰는 목록은 지킬에서 지원하지 않습니다.

목록은 각 항목이 동위성이 명확하게 인식되는 가능한 짧은 구절에 사용합니다. 항목의 내용이 길어질 경우 제목을 부여하여 하위 문단으로 분리합니다. 목록으로 사용하기에는 길고 제목을 부여하기에는 짧은 경우, 단순하게 문단만 나누어 사용 (각 항목 사이에 빈줄을 추가) 할 수 있습니다.

> **[NOTE]**  
> 목록의 사용을 다음과 같은 상황에 한정하면, 목록이 남용되는 것을 막으며 가독성을 향상시킬 수 있습니다.
>
> - 짧은 명사구로 된 항목의
> - **키워드**: 설명 형식의 항목

## 코드 블록 (Code Blocks)

**코드 블록**은 문서에 사용되는 코드나 시스템 명령과 같은, 마크다운 문법이나 사이트 디자인에 영향 받지 않는 내용을 작성해야 할 때 사용합니다.

인라인 코드 블록은 백틱 한 개 사이에 작성하고 (`｀Inline Code Block｀`), 여러 줄의 코드 블록은 백틱 세 개 (`｀｀｀`) 사이의 공간에 작성합니다.

코드 블록은 제목에는 사용하지 않습니다. 코드 블록과 강조가 동시에 적용되는 상황에서는 코드 블록만 사용합니다.

> **[NOTE]**  
> 강조와 코드 블록의 사용이 혼동되는 경우, **해당 구문을 그대로 복사하여 붙여넣기 할 수 있는지**를 고려하여 구분할 수 있습니다.
>
> e.g.
> - **현재 디렉토리의 경로**라는 표현은 복사/붙여넣기 할 필요가 없습니다.
> - **pwd** 명령어는 복사하여 리눅스 명령줄에 붙여넣을 수 있습니다.

## 수평선 (Horizontal Rules)

**수평선**은 문서 내 얇은 가로줄로 표현되는 부분으로, `---` 구문을 사용하여 표현합니다.

문서 본문과 머릿글, 꼬릿글 문단을 구분하는 용도로만 사용하여, 본문 내에서는 삽입하지 않습니다.

## 블록 인용 (Blockquotes)

**블록 인용**은 다른 출처에서의 내용을 변형 없이 그대로 인용할 경우에 사용합니다.

인용 블록 마지막에 출처 및 (가능하다면) 링크를 추가하는 것을 권장합니다.

블록 인용되는 내용은 원문의 형식을 유지하기 위해 강제 개행 (`  `: 띄어쓰기 두 칸) 하는 것을 허용합니다.

### 블록 인용 사용례

> 친구여, 나는 너의 하트를 빼앗으려 온 것이 아니다…  
> \- 줄리어스 시저, 3막, 2장
>
> \- Windows 9x의 **하트 게임 도움말 > 한마디...**에서 인용

블록 인용 구문은 다음 두 가지의 추가 사용법을 허용합니다.

- 문서 목록에 노출되기 위한, 문서 최상단의 요약 구절
- **[NOTE]**: 문서의 내용에 대한 추가 설명

### 추가 설명 사용례

> **[NOTE]**  
> 이 부분에는 본문에서 언급하기에는 논점을 벗어나지만, 언급하게 되면 읽는 이의 이해를 돕는 내용이 들어가 있습니다.
>
> 문서 개정에 대한 정보를 담을 때도 유용합니다.

## 기타 Markdown 외 문법 요소
### 윗 첨자 (Superscripts)

윗 첨자는 HTML의 윗 첨자 태그 (`**SUP**<sup>SUPerscript</sup>`) 를 사용합니다.

**윗 첨자**는 약어의 해설을 위해서만 사용하며, 해설받는 약어는 강조 구문으로 작성합니다. 문서 내에 약어가 최초 해설된 이후로는 사용하지 않습니다.

### 강제 개행

강제 개행 (`  `: 띄어쓰기 두 칸) 은 가능하면 사용하지 않습니다. 강제 개행이 사용된 부분은 문단을 나누거나 이전 문장의 다음에 이어서 작성하여야 합니다.

그러나 다음 상황에 한하여 강제 개행을 허용합니다.

- 이미지 캡션으로 사용하는 경우
- 블록 인용에서 원문이 강제 개행되었을 경우
- 목록을 사용할 수 없는 상황에서 항목을 나열해야 하는 경우

# 표준 문서 규격 및 작성 정책

이 문단에서는 블로그에 사용되는 표준 문서 규격과 문서 작성 시 적용되는 정책에 대해 다룹니다.

## 표준 문서 규격

```
---
title: title
excerpt: Post excerpt
categories:
  - category
tags:
  - tag 1
  - tag 2
---

Post abstract

---

# Content header 1

Content body

---

# Postscript header (Optional)

Postscript

```

## 작성 정책

문서 작성의 일관성을 유지하기 위한 표현 정책입니다.

### 경어체의 사용

문서 작성에 기본적으로 경어체를 사용합니다. 단, 다음과 같은 경우에는 평어체 및 기타 문체를 허용합니다.

- 개조식으로 서술되는 목록의 항목
- 이미지 캡션
- 인용 구절
- 취소선으로 처리되는 내용
- 기타 문서 구성 상 경어체 사용이 어색한 경우

### 원어 표현의 사용

원어 용어의 표현은 최초 등장시에만 원어로 표현하고, 이후에는 해당 용어의 가장 범용적인 국문 표현을 사용합니다.

단, 다음의 경우에는 2회 이상 등장 시에도 원어 표현을 사용합니다.

- 제목 구문
- 코드 블록
- 발음 표기가 불가능한 약어의 경우 (e.g. 에프티피 (x), FTP (o) / cf. 바이오스 (o), BIOS (x))
- 발음 표기가 가능하지만 범용적인 국문 표현이 없거나, 국문 표현의 혼동이 예상되는 경우 (e.g. S.M.A.R.T. (o), 스마트 (x))

반대로 다음의 경우에는 최초 등장시부터 국문 표현을 사용할 수 있습니다.

- 외래어이거나, 외래어에 준하는 용어 인식이 있는 경우 (e.g. 링크, 사이트, 스타일 등)
- 용어가 원어 + 국문의 조합으로 구성되어 있는 경우 (e.g. 문서 메타데이터 정보)
- 문서 작성에 참조한 출처에서 해당 용어를 국문으로 표현하고 있는 경우

### 소괄호 ()

소괄호 (`()`) 를 사용하는 경우, 앞뒤에 쉼표나 마침표 등의 기호가 있는 경우를 제외하면 각 소괄호 앞뒤를 띄어 씁니다. 단, 인용된 내용과 코드 블록에서는 예외를 허용합니다.

---

# 끝으로...

이 문서는 블로그 문서 작정 지침을 준수하여 작성되었습니다.