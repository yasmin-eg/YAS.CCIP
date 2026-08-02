# PROOF_OF_DOCUMENTATION

هذا الملف يُنشأ آليًا بواسطة مساعد GitHub لتوثيق حالة ملفات التوثيق الحالية في المستودع.

Repository: yasmin-eg/YAS.CCIP
URL: https://github.com/yasmin-eg/YAS.CCIP
Default branch: main
Snapshot time (UTC): 2026-08-02T00:00:00Z

Commit OID (current): 2d4112dea13b8e0183cb038eea92a4b77fe0f15b

Files recorded in this snapshot:

- README.md
  - Git blob SHA: 93e54a2bbdf415071e40e5c422befb610e4b687a
  - Source URL: https://github.com/yasmin-eg/YAS.CCIP/blob/main/README.md

- SECURITY.md
  - Git blob SHA: 6a17621d0d42c2b11e535ec8f77bba19b1c655de
  - Source URL: https://github.com/yasmin-eg/YAS.CCIP/blob/main/SECURITY.md

- License / رخصة
  - File (long title) present at root
  - Referenced in repo root listing

Purpose of this file
--------------------
هذا ملف دليلية (proof) يَجْمَع البينات التالية:
1. بصمة Git (blob SHA) للملفات الأساسية (README.md, SECURITY.md) كما وُجدت في الفرع `main` في وقت الالتقاط أعلاه.
2. معرف الالتزام (commit OID) الذي يحتوي على هذه النسخ من الملفات.

لماذا هذا مفيد؟
- أرقام الـ blob SHA وcommit OID تمثل إثباتًا أنه في وقت التوثيق هذه الملفات كانت تحتوي على المحتوى المشار إليه. أي تغيير لاحق في الملفات سيغيّر الـ blob SHA وcommit OID.

الخطوات التالية (لإضافة توقيع تشفيري قابل للتحقق):
1) على جهازك المحلي، انسخي المستودع (أو استخدمي نسخة العمل الحالية):
   git clone git@github.com:yasmin-eg/YAS.CCIP.git
   cd YAS.CCIP

2) أنشئي ملف تجزئة موحد لجميع الملفات المهمة (SHA256SUMS):
   find . -type f -name '*.md' -not -path './.git/*' -print0 | sort -z | xargs -0 sha256sum > SHA256SUMS

   ملاحظة: يمكنك تخصيص قائمة الملفات حسب حاجتك (مثلاً استثناء ملفات لغة أو docs/ أخرى).

3) أوقعي (sign) ملف SHA256SUMS باستخدام مفتاح GPG الخاص بك (سيُنتج ملف SHA256SUMS.asc):
   gpg --armor --output SHA256SUMS.asc --detach-sign SHA256SUMS

   للتحقق محليًا:
   gpg --verify SHA256SUMS.asc SHA256SUMS

4) أضيفي الملفات الموقعة إلى المستودع واعملي commit موقّع (GPG-signed commit):
   git add SHA256SUMS SHA256SUMS.asc
   git commit -S -m "Add signed manifest (SHA256SUMS) documenting docs snapshot"
   git push origin main

   ملاحظة: لتوقيع الكوميت تلقائيًا تأكدي من إعداد git:
     git config user.signingkey <GPG_KEYID>
     git config commit.gpgSign true

5) (اختياري) أنشئي tag موقع بالـ GPG لمزيد من الثبوت:
   git tag -s v1.0-docs -m "Signed snapshot of documentation"
   git push origin v1.0-docs

6) (اختياري) اصنعي Release مرفقًا بالملفات الموقعة عبر GitHub UI أو gh CLI:
   gh release create v1.0-docs --title "Snapshot v1.0-docs" --notes "Signed manifest and signatures" SHA256SUMS SHA256SUMS.asc

ملاحظات أمنية وقانونية
----------------------
- التوقيع GPG والـ commit الموقّع تظهر "Verified" على GitHub فقط إذا كان المفتاح العام المستخدم مرفوعًا في: https://github.com/settings/keys (GPG keys).
- لا أستطيع توقيع الملفات نيابةً عنك لأن توقيع GPG يحتاج المفتاح الخاص (private key) الموجود محليًا لديك. هذا الملف يوفّر سجلًا رقميًا (blob SHA + commit OID) كخطوة أولى قبل توقيعك المحلي.

متى تنفذين؟
----------
إذا تريدين، أقدر أُنشئ أيضًا ملف SHA256SUMS هنا على المستودع (بدون التوقيع) وذلك بتضمين التجزئات التي أنتِ توافقين عليها. ومع ذلك، لأن توليد التجزئات يتطلب حساب SHA256 من المحتوى الفعلي، أفضّل أن تُشغّلي الأوامر المحلية أعلاه ثم ترفعي SHA256SUMS وSHA256SUMS.asc عبر commit موقّع بنفسك.

إذا موافقة، سأضيف هذا الملف التوثيقي (PROOF_OF_DOCUMENTATION) للمستودع الآن.