| Note : این ترجمه ی  [مقاله ای](https://imsadra.me/commit-like-a-pro) هست که [صدرا](https://imsadra.me) نوشته 

کامیت زدن یکی از رایج ترین کارهایی هست که برنامه نویس ها انجام میدن تغییرات رو استیج میکنی و کامیت میزنی تا بعدا داخل [تاریخچه](https://git-scm.com/book/en/v2/Git-Basics-Viewing-the-Commit-History) قابل بررسی باشن. اما قاعده های کامیت زدن چی ؟ اصلا تفاوتی بین یه کامیت کثیف و تمیز هست ؟ از ایموجی میشه توی کامیت ها استفاده کرد؟ در این مقاله، مخوایم درمورد قاعده های متداول کامیت زدن و بست پرکتیس های `git commit`  صحبت کنیم تا کامیت های تمیز تری داشته باشیم.
## 1. مرحله ی استیج کردن
تغییراتتون رو مثل یک بازیگر ببینید. اونها باید چیزی برای نمایش داشته باشن قبل از اینکه کامیت بشن. اگه خوب بازی کنن، به اندازه کافی قابل هستن که تبدیل به کامیت بشن، در غیر اینصورت نادیده گرفتن میشن. پس با عقل جور درنمیاد که تغییراتتون درست اجرا نکنن و بعد به کامیت تبدیل بشن. 
#### 1.1. کی و چی رو استیج کنیم
باید مطمئن بشید که رابطه ای بین تغییراتی که انجام میدید باشه. اگر میتونید تغییراتتون رو در چند کلمه توصیف کنید تا برنامه نویس یا برنامه نویس های بعدی به راحتی بتونن از کامیت مسیج هاتون متوجه کارهایی که کردید بشن، خیالتون راحت باشه. حتی با اینکه میتونین یه کامیت مسیج چندین خطه داشته باشین،  هیچوقت تغییرات رو با هم یکی نکنین.
## 2. مرحله ی کامیت زدن
هیچ مشکلی نداره اگه صدها کامیت توی تاریخچه ی کامیت هاتون داشته باشین. گیت یک manifest (تصویر) از فایل های پروژه ی شما ذخیره میکنه پس نگران از دست رفتن منابع و فضا نباشید.
#### 2.1. چی کامیت کنیم
گیت  سیستم کنترل نسخه ی Line-Based (بر پایه خط) هست. گیت خط هایی که تغییر کردند رو  بررسی میکنه نه حرف یا کلمه ای که تغییر کرده. اگر یک کاراکتر از یک خط رو تغییر بدید، اون *خط* بررسی میشه نه اون کاراکتر. همونطور که قبلا یاد گرفتیم، مطمئن بشید خط هایی که تغییر دادید به هم مرتبط هستن چون دست به دست همدیگه میدن تا یک قابلیت رو بسازن یا کاری رو انجام بدن.
#### 2.2. چگونه تکه کدهارو توی کامیت ها یکی کنیم
شما میتونید چندین فایل داشته باشید که در بخش هایی تغییر کرده اند و اون بخش هارو اضافه، استیج و در نهایت برای کامیت کردن آمادشون کنید. 
یک پروژه ی وبسایت رو در نظر بگیرید که چند فایل CSS و JS داره. تصور کنید که چند خط به فایل index اضافه و در فایل CSS به styleشون تغییراتی اعمال میکنین.
در همین حال یه Function (تابع) برای یه فرم توی یه فایل JS درست میکنین. خیلی راحت میتونین از ‍`git add --patch`  استفاده کنید تا اون بلاک های کد به خصوص رو با جواب دادن چندتا سوال استیج کنید.
#### 2.3 کامیت مسیج ها
کامیت مسیج جایی هست که شما با کسی که قراره در همون خط یا خط ها  Contribution (مشارکت) انجام بده  ارتباط میگیرید. بزارید  وقتی کامیت مسیج شمارو میخونه احساس رضایت کنه. وقتی میخواید تغییرات استیج شده رو کامیت کنید، باید براشون  یه مسیج قرار بدید. هر کامیت یه عنوان ، یک سری توضیحات و Metadata (فراداده) داره. برنامه نویس باید عنوان رو پر کنه، اما پر کردن توضیحات اختیاریه. بهترین کار اینه که کامیت رو کوتاه و قابل فهم نگه دارین تا بقیه برنامه نویس ها بتونن کامیت هاتون رو از طریق خوندن عنوانش بفهمن.
#### 2.4. مدیریت ایشیو ها از طریق کلمات کلیدی در کامیت مسیج ها
بعضی از سرویس هایی که از گیت به عنوان مدیر Repository (مخزن) خودشون استفاده میکنن، مثل گیتهاب، از این هم جلو تر رفتن و قابلیت های خاصی برای گیت دارن. برای مثال اگه از کلمات کلیدی ‍‍‍‍ ‍‍‍‍`Close` , `Closes` , `Closed`,`Fix` و... قبل از تگ ایشیوتون استفاده کنید و وقتی که `HEAD` تون برابر با اون کامیت بشه، اون ایشیو اتوماتیک بسته میشه. درمورد این قابلیت بیشتر توی گیتهاب [بخونید](https://docs.devart.com/studio-for-sql-server/source-controlling-databases/associating-commits-with-github-issues.html). 
```bash
$ git commit -m `deprecation fixed Closes #215`
```
| *تشکر از  [Conor Sheehan](https://imsadra.me/@ConorSheehan1) که این قابلیت رو معرفی کرد* !
#### 2.5. از ایموجی استفاده نکنید
من Repostiroy (مخزن) هایی رو دیدم که قواعد خاص خودشون رو برای کامیت زدن دارن. بعضی هاشون از ایموجی ها استفاده میکنن تا وضعیت یه کامیت رو نشون بودن که مثلا یه باگ رو فیکس کرده یا برای تسته یا هرنوع دیگه ای.
من به شخصه از ایموجی توی کامیت مسیج هام استفاده نمیکنم. شاید Contributor (مشارکت کننده) هایی از پلتفورم ها و Interface (رابط کاربری) های مختلف داشته باشین. از اونجایی که ایموجی ها از کد های ASCII خاص (که به طور معمول توسط Interface (رابط کاربری) های Text-Based (برپایه متن) مثل CLI( رابط کاربری خط فرمان) و سیستم های Unicode استفاده میکنن و معمول ترین CLI (رابط کاربری خط فرمان) ها نیاز به Package (بسته) ها یا فونت های مختلف دارن تا بتونن ایموجی هارو نشون بدن. این قاعده ممکنه برای همه خوب نباشه. بعضی ها شاید برای خوندن تاریخچه کامیت ها به مشکل بخورن. (مثل کاراکتر ایموجی توی عنوان کامیت مسیج که ممکنه به شکل کاراکتر ASCII یا علامت سوال نشون داده بشه)
![Example](link later)
 این حالت بست پرکتیس اینه که از یه prefix pattern (الگوی پیشنود) برای دسته بندی کامیت ها استفاده کرد. مثل bracket (براکت) یا پرانتز. یا مثلا مثل عکس پایین که از قاعده ی `type: message` استفاده کرده
![Example](link later)

#### 2.6. توضیحات کامیت مسیج 
اگه تغییراتتون رو استیج کنید و وقتی که میخواید کامیت بزنید، ادیتورتون رو باز کنید که یه پیغام وارد کنید، میتونید اطلاعات اضافه تر مثل TODO ها، باگ ها و... رو وارد کنید. اما هنوز قسمت عنوان مهم ترین بخشه.
با وجود اینکه قسمت توضیحات اختیاریه ، هر مقدار که دلتون میخواد میتونید توضیحات بنویسید. اگه تغییراتتون کمی پیچیده هستن و نیاز به توضیحات بیشتر دارن، میتونید درمورد بخش های مختلف تغییراتتون بیشتر توضیح بدین.
![Example](link later)

در آخر، میتونیم به سادگی بگیم که اگه کامیت هاتون و کامیت مسیج هاتون رو کوتاه و ساده نگه دارید، تقریبا نصف راهو رفتید.
### 3. قاعده های مختلف گیت
گیت اصلا قاعده نداره. قاعده ها توسط شرکت ها و تیم ها ساخته میشن. یه تیم شاید استفاده از ایموجی هارو صلاح ببینه اما یه تیم دیگه همه چیزو ساده نگه داره. یه تیم شاید مستقیم به `main` پوش کنه (که به قاعده ی single-branch معروفه.) ولی یه تیم دیگه یه برنچ `development‍` هم داشته باشه و فقط کامیت های انتشار نسخه رو به برنچ `main` پوش کنه اگه دارید جایی کار میکنید و از قاعده هاشون خوشتون نمیاد، بهتره بهش عادت کنید. زمانی که برای تغییر ذهنیت اون تیم صرف میکنید، میتونه برای حل کردن چندتا باگ صرف بشه.
## نتیجه گیری
در این مقاله، ما قاعده های ساده ی `git commit` و بست پرکتیس هاش رو فهمیدیم. درمورد خوبی ها و بدی های هر پرکتیس صحبت کردیم و در نهایت، متوجه شدیم که گیت فاعده هارو نمیسازه ، بلکه این کمپانی ها و استارت آپ ها هستن که اونارو میسازن.
