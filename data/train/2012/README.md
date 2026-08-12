# 2012 Constitutional Law — Source Packet

Status: **TRAIN source packet / prospective Phase B invalidated**

The 2012 clean prospective test was lost before a prediction commit; see `CONTAMINATION.md`. The year remains valid TRAIN data for teacher-signal-guided extraction and model fitting.

## Primary source metadata

The Ministry of Justice official pages confirm publication of the 2012 judicial-exam materials:

- `平成２４年司法試験問題` — official problem index, including the essay public-law PDF.
- `平成２４年司法試験の結果について` — official result page, including `論文式試験出題の趣旨` and `採点実感等に関する意見` PDFs.

The official problem-only PDF URL identified during retrieval was:

```text
https://www.moj.go.jp/content/000098335.pdf
```

Direct PDF retrieval returned HTTP 403 in the current environment.

## Machine-readable transcription used for extraction

BEXA page:

```text
平成24年新司法試験公法系第1問（憲法）
https://bexa.jp/papers/view/58
```

The page contains, in sequence:

```text
problem text
→ 出題趣旨 transcription
→ 採点実感 transcription
```

Because the official PDFs could not be parsed directly in the current retrieval environment, the substantive extraction below uses the BEXA transcription while treating the Ministry of Justice pages as the authority for the existence and identity of the official source artifacts.

## Core problem shape

A village gives post-fire reconstruction aid to the village's only Buddhist temple. The aid is itemized for:

```text
land / cemetery restoration: 25 million yen
main hall reconstruction:     40 million yen
priest residence reconstruction: 10 million yen
```

Resident D asks what litigation to bring and what constitutional claim to make. A second question asks for the examinee's own view while anticipating the defendant's response.

The constitutional center is public financial support to a religious organization and the relationship among Article 89 first sentence, Article 20(1) second sentence, and Article 20(3).

## Teacher-signal themes used

The official-material transcription emphasizes:

- resident litigation as the main litigation form, with the statutory basis identified to the paragraph/item level;
- Article 89 first sentence as the primary constitutional entry point;
- classification of A Temple as a `宗教上の組織若しくは団体`;
- the relationship with Article 20(1) privilege prohibition and Article 20(3) religious-activity prohibition;
- whether Article 89's public-money prohibition is absolute or should be understood through the broader separation-of-state-and-religion framework;
- use of the Tsu Jichinsai, Ehime Tamagushiryo, Minoo memorial, and Sorachibuto Shrine precedents;
- concrete, item-by-item analysis of cemetery/land, main hall, and priest residence;
- rejection of simplistic `public character -> constitutional` reasoning;
- rejection of implausible plaintiff/defendant positions created merely to manufacture contrast.

## Integrity note

2012 must not be cited as frozen-model prospective generalization evidence. It may be cited only as TRAIN compatibility / growth evidence.
