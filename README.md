# ModooMaker/test-2 — Minimal Mistakes 테마 Fork

Jekyll 테마 Minimal Mistakes 4.18.1을 가져와 사이트 설정을 살펴본 저장소입니다. 테마 자체와 아래 기능은 원작자 Michael Rose 및 기여자들의 작업입니다.

## 목적과 현재 범위

개인·동아리 사이트에 사용할 테마 구성을 검토한 과거 실험 후보입니다. `lee-junyeol`의 설정 변경 커밋이 확인되지만, 원작 테마의 전체 기능을 이 저장소에서 새로 구현한 것으로 소개하지 않습니다.

현재 소스에는 글·페이지·아카이브·검색·splash 레이아웃, Sass 스타일과 JavaScript, 문서·샘플 페이지가 있습니다. 구체적인 도입 프로젝트나 독자적인 기능 개발 범위는 기록되어 있지 않습니다.

## 기술 스택과 구조

- Jekyll, Liquid, Ruby gemspec, Markdown
- Sass/CSS, jQuery와 테마 플러그인
- npm 기반 JavaScript 압축·배너 생성
- 과거 Travis CI 설정

[_layouts/](_layouts/)와 [_includes/](_includes/)가 화면 구조를, [_sass/](_sass/)와 [assets/](assets/)가 스타일·클라이언트 자산을 담당합니다. [gemspec](minimal-mistakes-jekyll.gemspec)은 테마 버전 4.18.1과 Jekyll 의존성을 선언합니다. 앱 전용 백엔드나 DB는 없습니다.

## 화면과 참고 데모

이 Fork는 GitHub Pages가 비활성화되어 있고 별도 배포 데모를 확인하지 못했습니다. 저장소의 [레이아웃 예시 이미지](screenshot-layouts.png)와 [기존 테마 이미지](screenshot.png)는 원작 자료입니다. [원작 테마 문서](https://mmistakes.github.io/minimal-mistakes/)의 예시는 이 Fork의 배포 결과가 아닙니다.

## 설치와 확인 방법

Ruby와 Bundler가 필요합니다. 아래는 저장소의 Gemfile·샘플 구조에 따른 빌드 확인 경로이며, 현재 환경에서 설치·성공 여부를 재현하지 않았습니다.

```bash
git clone https://github.com/ModooMaker/test-2.git
cd test-2
bundle install
bundle exec jekyll build --source test --destination /tmp/minimal-mistakes-site
```

[Rakefile](Rakefile)에는 `preview` 작업도 있지만 추가 `listen` 로딩과 환경 구성이 필요합니다. JavaScript를 다시 생성하려면 [package.json](package.json)의 `build:js`를 확인하세요. 단순히 테마를 읽는 데 자산 재생성은 필요하지 않습니다.

## 테스트와 현재 한계

- 전용 제품 테스트는 없습니다. `test/`는 테마를 확인할 샘플 사이트이며 자동 단위 테스트가 통과했다는 의미가 아닙니다.
- [.travis.yml](.travis.yml)은 Ruby 2.4와 `docs/Gemfile`을 사용해 Algolia 관련 빌드를 실행하는 과거 설정입니다. 현재 CI가 통과한다는 근거로 사용하지 않습니다.
- 오래된 의존성과 설정을 그대로 포함합니다. 현재 Ruby/Node 환경의 설치·빌드, 외부 검색 연동과 브라우저 호환성은 미검증입니다.
- 2026-11-13 문서 점검은 기본 브랜치 소스·의존성·Fork 관계와 README 파일 링크 확인에 한정했습니다.

## 원작과 관련 링크

- [Minimal Mistakes 원작 저장소](https://github.com/mmistakes/minimal-mistakes)
- [Michael Rose](https://mademistakes.com), [GitHub](https://github.com/mmistakes), [기존 소셜 링크](https://twitter.com/mmistakes)
- [테마 문서 소스](docs/), [변경 이력](CHANGELOG.md), [LICENSE](LICENSE)

아이콘·데모 이미지·라이브러리의 기존 출처와 저작권·라이선스 고지는 아래에 원문으로 보존합니다. 원작의 코드·이미지와 이 Fork의 설정 작업을 구분해야 합니다.

## Credits

### Creator

**Michael Rose**

- <https://mademistakes.com>
- <https://twitter.com/mmistakes>
- <https://github.com/mmistakes>

### Icons + Demo Images:

- [The Noun Project](https://thenounproject.com) -- Garrett Knoll, Arthur Shlain, and [tracy tam](https://thenounproject.com/tracytam)
- [Font Awesome](http://fontawesome.io/)
- [Unsplash](https://unsplash.com/)

### Other:

- [Jekyll](http://jekyllrb.com/)
- [jQuery](http://jquery.com/)
- [Susy](http://susy.oddbird.net/)
- [Breakpoint](http://breakpoint-sass.com/)
- [Magnific Popup](http://dimsemenov.com/plugins/magnific-popup/)
- [FitVids.JS](http://fitvidsjs.com/)
- [GreedyNav.js](https://github.com/lukejacksonn/GreedyNav)
- [Smooth Scroll](https://github.com/cferdinandi/smooth-scroll)
- [Gumshoe](https://github.com/cferdinandi/gumshoe)
- [jQuery throttle / debounce](http://benalman.com/projects/jquery-throttle-debounce-plugin/)
- [Lunr](http://lunrjs.com)

---

## License

The MIT License (MIT)

Copyright (c) 2013-2020 Michael Rose and contributors

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.

Minimal Mistakes incorporates icons from [The Noun Project](https://thenounproject.com/) 
creators Garrett Knoll, Arthur Shlain, and tracy tam.
Icons are distributed under Creative Commons Attribution 3.0 United States (CC BY 3.0 US).

Minimal Mistakes incorporates [Font Awesome](http://fontawesome.io/),
Copyright (c) 2017 Dave Gandy.
Font Awesome is distributed under the terms of the [SIL OFL 1.1](http://scripts.sil.org/OFL) 
and [MIT License](http://opensource.org/licenses/MIT).

Minimal Mistakes incorporates photographs from [Unsplash](https://unsplash.com).

Minimal Mistakes incorporates [Susy](http://susy.oddbird.net/),
Copyright (c) 2017, Miriam Eric Suzanne.
Susy is distributed under the terms of the [BSD 3-clause "New" or "Revised" License](https://opensource.org/licenses/BSD-3-Clause).

Minimal Mistakes incorporates [Breakpoint](http://breakpoint-sass.com/).
Breakpoint is distributed under the terms of the [MIT/GPL Licenses](http://opensource.org/licenses/MIT).

Minimal Mistakes incorporates [FitVids.js](https://github.com/davatron5000/FitVids.js/),
Copyright (c) 2013 Dave Rubert and Chris Coyier.
FitVids is distributed under the terms of the [WTFPL License](http://sam.zoy.org/wtfpl/).

Minimal Mistakes incorporates [Magnific Popup](http://dimsemenov.com/plugins/magnific-popup/),
Copyright (c) 2014-2016 Dmitry Semenov, http://dimsemenov.com.
Magnific Popup is distributed under the terms of the MIT License.

Minimal Mistakes incorporates [Smooth Scroll](http://github.com/cferdinandi/smooth-scroll),
Copyright (c) 2019 Chris Ferdinandi.
Smooth Scroll is distributed under the terms of the [MIT License](http://opensource.org/licenses/MIT).

Minimal Mistakes incorporates [Gumshoejs](http://github.com/cferdinandi/gumshoe),
Copyright (c) 2019 Chris Ferdinandi.
Smooth Scroll is distributed under the terms of the [MIT License](http://opensource.org/licenses/MIT).

Minimal Mistakes incorporates [jQuery throttle / debounce](http://benalman.com/projects/jquery-throttle-debounce-plugin/),
Copyright (c) 2010 "Cowboy" Ben Alman.
jQuery throttle / debounce is distributed under the terms of the [MIT License](http://opensource.org/licenses/MIT).

Minimal Mistakes incorporates [GreedyNav.js](https://github.com/lukejacksonn/GreedyNav),
Copyright (c) 2015 Luke Jackson.
GreedyNav.js is distributed under the terms of the [MIT License](http://opensource.org/licenses/MIT).

Minimal Mistakes incorporates [Jekyll Group-By-Array](https://github.com/mushishi78/jekyll-group-by-array),
Copyright (c) 2015 Max White <mushishi78@gmail.com>.
Jekyll Group-By-Array is distributed under the terms of the [MIT License](http://opensource.org/licenses/MIT).

Minimal Mistakes incorporates [@allejo's Pure Liquid Jekyll Table of Contents](https://allejo.io/blog/a-jekyll-toc-in-liquid-only/),
Copyright (c) 2017 Vladimir Jimenez.
Pure Liquid Jekyll Table of Contents is distributed under the terms of the [MIT License](http://opensource.org/licenses/MIT).

Minimal Mistakes incorporates [Lunr](http://lunrjs.com),
Copyright (c) 2018 Oliver Nightingale.
Lunr is distributed under the terms of the [MIT License](http://opensource.org/licenses/MIT).
