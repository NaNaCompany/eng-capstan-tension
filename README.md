# 캡스턴 로프 한계장력 계산기

드럼에 감긴 로프가 미끄러지기 직전에 지탱할 수 있는 큰 쪽 장력을 계산합니다.

- ID: E125
- App: https://nanalab.kr/eng-capstan-tension/
- Repository: https://github.com/NaNaCompany/eng-capstan-tension
- Formula: Tₗ = Tₛ exp(μₛ θ)

## Model and data

질량과 굽힘강성을 무시하는 유연한 로프, 일정한 정지마찰계수, 드럼과의 연속 접촉을 가정합니다. θ는 전체 접촉 감김각이며 여러 바퀴를 입력할 수 있습니다. 출력은 로프의 파단장력이나 드럼 강도가 아닙니다. 로프에 추가되는 독립 하중·홈 형상 효과는 제외합니다.

Inputs normalize to SI. Repeated-input models support adding/removing actual input rows. Calculations, finite-number checks and physical-domain checks run locally; no external property database or solver API is used.

## Validation

Run node --test tests/*.test.mjs and python scripts/build-locales.py --check. tests/reference.json contains independently computed high-precision default and boundary references. The source notices distinguish original MIT work from citation-only external references.

## Static languages

Korean (existing root), English (`en/`), Spanish (`es/`), Simplified Chinese (`zh/`), Japanese (`ja/`) and German (`de/`). Each page has its own canonical URL, reciprocal hreflang, localized metadata, interface, validation messages and preview image. The language links work without JavaScript. Calculation code is shared and no runtime translation API is used.

Edit `localization/*.json` for text, `src/template.html` for the shared page, and run `python scripts/build-locales.py`. Run `python scripts/build-locales.py --check` and `npm test` before publishing. Decimal commas are accepted in Spanish and German; thousands separators are not supported.
