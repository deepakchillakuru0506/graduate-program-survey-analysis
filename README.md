# Graduate Program Survey Analysis — University of Tampa

A mixed-method study of graduate-student satisfaction at a private university: what students think
of the program, which factors actually drive their satisfaction, and which student segments the
program is failing. Delivered as a course project in **MKT 617 (Marketing Analytics)**, Fall 2024.

**Team project — 5 analysts.** Mary Blejwas, Maggie Kilmon, Praneeth Reddy Tene, Anjila Subedi,
Deepak Kumar Reddy Chillakuru. Course: MKT 617, Section 1, Dr. Jennifer Burton, John Sykes College
of Business, December 2024.

**My contribution:** survey administration in Qualtrics, the segmentation analysis (hierarchical
and K-means clustering, segment profiling and descriptor analysis), the regression-based driver
model and its validation via gain/lift analysis, and the group's recommendations write-up.

## The problem

The university knew its graduate enrollment was not growing the way its undergraduate enrollment
was, but had no structured read on how current graduate students rated the program, what they
valued, or where it was losing them. The brief: measure perceived program effectiveness against
students' academic, professional, and personal goals, and turn that into marketing priorities.

## Data

| | |
|---|---|
| Responses | 133 current graduate students (~13.3% of enrollment) |
| Instrument | 18-question survey: demographics, 9 satisfaction measures, importance ranking, one open-ended item |
| Collection | Distributed by the graduate program office to all current graduate students, anonymous and voluntary |
| Open-ended responses | 80 (used for sentiment analysis) |

The survey instrument is reproduced in [`survey-instrument.md`](survey-instrument.md).

**Design limitations, stated up front:** opt-in distribution means respondents self-selected, and
people who answer a satisfaction survey usually hold stronger views than the population. The
response mix skewed toward the M.S. Business Analytics program, so segment sizes should be read as
directional rather than as university-wide estimates.

## Approach

Three analyses, mixed-method, run in Enginius:

1. **Segmentation** — hierarchical clustering (Ward) to find the number of segments from the scree
   plot, then K-means with the chosen k, profiled against descriptor variables (program, age band,
   international status).
2. **Predictive modeling** — regression with overall satisfaction (Q4) as the dependent variable
   against career alignment, likelihood to recommend, the nine satisfaction measures, and the
   importance ranking, then validated with a gain chart and lift ratios.
3. **Sentiment analysis** — RAKE keyword extraction over the 80 open-ended responses, coded into
   emotion categories, plus a valence split of positive vs negative sentiment.

## Findings

**What drives satisfaction.** Professor knowledge, the relevance of projects and tools to the
career the student is pursuing, and course variety were the strongest positive drivers of overall
satisfaction. Students who rate the program highly are also far likelier to recommend it. The
model explained roughly 70% of the variance in satisfaction and outperformed random selection by
about 43% at the top decile — useful for prioritising where to act, not a forecasting instrument.

**What students are unhappy about.** Career services assistance, networking opportunities, course
variety/availability, and employment opportunities were the consistent weak spots, and they showed
up in all three analyses rather than in one.

**Three segments exist, and they want different things.**

| Segment | Share | What they value | Where they are unhappy |
|---|---|---|---|
| Satisfied advocates | 54% (hierarchical) | Program effectiveness, course variety, flexibility; very likely to recommend | Career services, networking, employment support |
| Career-focused | 18% | Clubs and events, professor knowledge, employment prospects | Course variety and flexibility |
| Dissatisfied | 28% | Networking and career services | Overall program fit — least likely to recommend |

Descriptor analysis located the dissatisfaction: students aged 20–25 concentrated in the
least-satisfied segment, while respondents over 30 clustered in the most satisfied one. Programs
like Nursing and Social and Emerging Media differentiated positively; Exercise and Nutrition
Science and the youngest age band look like candidates for tailored marketing.

**Sentiment was net positive but not uniformly so.** Trust (25%), anticipation (21%), and joy
(16%) led the emotional coding; 19.4% of the responses carrying positive or negative valence were
negative. Negative comments concentrated on advisor support, grading consistency, tuition and fees,
and course availability — with employment and internship support recurring among
international students.

## Recommendations delivered

1. Run the satisfaction survey every semester so the metric becomes trackable rather than a
   one-off.
2. Stand up a student advisory board — near-zero cost, and it creates a feedback loop the program
   currently lacks.
3. Have graduate professors also serve as advisors, mirroring the undergraduate model, to fix
   elective selection, degree tracking, and mentorship in one move.
4. Fund and promote graduate-specific career fairs, including one aimed at employers open to
   sponsorship, and fix the reach of existing career programming.
5. Move to a rolling course schedule with evening sections so students can plan their degree
   without availability surprises.

## Repository contents

| File | What it is |
|---|---|
| `survey-instrument.md` | The 18-question survey as fielded |
| `findings_summary.csv` | Headline aggregate metrics, one row per finding |

## What is deliberately not here

The respondent-level survey data and the verbatim open-ended comments are **not** published. The
consent statement shown to participants scoped their responses to a course assignment, which does
not extend to public release, and small programmes with identifiable demographics make
re-identification a real risk even from anonymised rows. The aggregate findings above are the
defensible output of the study.
