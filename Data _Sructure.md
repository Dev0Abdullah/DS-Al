# Data Structures

الـ Data Structure هي طريقة لتخزين البيانات بشكل منظم في الذاكرة (الميموري) عشان تقدر تسترجعها وتشتغل عليها بسرعة وكفاءة.

لو البيانات مش متخزنة بشكل صحيح، هتلاقي البرنامج بيشتغل ببطء. التنظيم الجيد للبيانات يساعدك على تحسين أداء البرنامج.

🌟 **ملاحظة:** التخزين الفعّال للبيانات بيخلي البرمجة أسهل وأسرع!

---

## كيف بيشتغل البرنامج في الذاكرة؟

البرنامج بتاعنا لما بيشتغل، الذاكرة بتتقسم لثلاث أجزاء رئيسية: **الـ Code**، **الـ Stack**، و **الـ Heap**. كل جزء ليه دور معين:

### 1. **الـ Code**:
ده الجزء اللي بيخزن فيه البرنامج نفسه (الكود اللي كتبته). يعني لو عندك دوال (Functions) أو أكواد بتنفذ حاجة معينة، بتتحفظ هنا.

### 2. **الـ Stack**:
الـ Stack هو المخزن المؤقت (Temporary Storage). كل المتغيرات المحلية (Local Variables) اللي بتتعلق بالدوال بتتخزن هنا. لما الدالة تخلص، الذاكرة بتاعت المتغيرات دي بتتحذف أوتوماتيكي.

### 3. **الـ Heap**:
الـ Heap هو المكان المخصص للكائنات (Objects) أو البيانات اللي محتاجة تفضل موجودة لفترة أطول. بيتميز بمساحة أكبر لكنه أبطأ شوية في الوصول من الـ Stack.

---

**ملاحظة:** 
- **الـ Code**: هو الكود بتاع البرنامج.
- **الـ Stack**: بيخزن المتغيرات المحلية.
- **الـ Heap**: بيخزن الكائنات والبيانات طويلة العمر.

---

### تقسيم الميموري:
![Memory Segmentation](https://www.simplilearn.com/ice9/free_resources_article_thumb/Memory_Segmentation.png)

---

## الـ Static vs. Dynamic Memory

اللي شرحناه لغاية دلوقتي كان عن **الـ Static Memory**، لكن في حاجة تانية اسمها **Dynamic Memory**.

**الـ Dynamic Memory** هي نوع من الذاكرة بتسمح للمستخدم بتحديد المساحة اللي هتتحجز في الميموري أثناء تنفيذ البرنامج، بدل ما تحددها مسبقًا زي ما في الـ Static Memory. في النوع ده، ممكن نخصص مساحة ميموري في الوقت الفعلي بناءً على احتياج البرنامج.

### مثال على الـ Dynamic Memory Allocation:

```cpp
#include <iostream>
using namespace std;

int main() {
    int i;
    // Pointer To Determine Address Of Variable
    float *ptr;
    cout << "Enter An Array Size ?: ";
    cin >> i;
    // Dynamic Memory Allocation
    ptr = new float[i];
    if(ptr == NULL) {
        cout << "Memory Not Allocated" << endl;
        exit(0);
    }
    cout << "Enter Array Elements: ";
    for(int j = 0; j < i; j++) {
        cin >> ptr[j];
    }
    cout << "Array Elements: ";
    for(int j = 0; j < i; j++) {
        cout << ptr[j] << " ";
    }
    // Free Memory  
    delete [] ptr;
    return 0;
}
