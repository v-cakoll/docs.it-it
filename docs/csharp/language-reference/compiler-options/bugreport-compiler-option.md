---
title: -bugreport (opzioni del compilatore C#s)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- /bugreport
dev_langs:
- CSharp
helpviewer_keywords:
- /bugreport compiler option [C#]
- -bugreport compiler option [C#]
- bugreport compiler option [C#]
ms.assetid: f39665e3-4f6f-4357-88a2-3274c7bec0c1
caps.latest.revision: 20
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: ccfea1aa7e51ad013418f61bc4478034c9a5d830
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="bugreport-c-compiler-options"></a>/bugreport (opzioni del compilatore C#)
Specifica che le informazioni di debug devono essere inserite in un file per analisi successive.  
  
## <a name="syntax"></a>Sintassi  
  
```console  
/bugreport:file  
```  
  
## <a name="arguments"></a>Argomenti  
 `file`  
 Nome del file in cui si vuole inserire il report sui bug.  
  
## <a name="remarks"></a>Note  
 L'opzione **/bugreport** specifica che le informazioni seguenti devono essere inserite in `file`:  
  
-   Una copia di tutti i file di codice sorgente nella compilazione.  
  
-   Un elenco delle opzioni del compilatore usate nella compilazione.  
  
-   Informazioni sulla versione per il compilatore, il runtime e il sistema operativo.  
  
-   Assembly e moduli di riferimento, salvati come cifre esadecimali, ad eccezione degli assembly forniti con .NET Framework e SDK.  
  
-   L'eventuale output del compilatore.  
  
-   Una descrizione del problema, che verrà richiesta.  
  
-   Una descrizione del modo in cui si può risolvere il problema, che verrà richiesta.  
  
 Se questa opzione viene usata con **/errorreport:prompt** o **/errorreport:send**, le informazioni nel file verranno inviate a Microsoft Corporation.  
  
 Dato che una copia di tutti i file di codice sorgente verrà inserita in `file`, potrebbe essere utile riprodurre il sospetto difetto del codice nel programma più breve possibile.  
  
 Questa opzione del compilatore non è disponibile in Visual Studio e non può essere modificata a livello di codice.  
  
 Si noti che contenuto del file generato espone il codice sorgente e ciò potrebbe causare la divulgazione accidentale di informazioni.  
  
## <a name="see-also"></a>Vedere anche  
 [C# Compiler Options](../../../csharp/language-reference/compiler-options/index.md)  (Opzioni del compilatore C#)  
 [/errorreport (opzioni del compilatore C#)](../../../csharp/language-reference/compiler-options/errorreport-compiler-option.md)   
 [Gestione delle proprietà di progetti e soluzioni](/visualstudio/ide/managing-project-and-solution-properties)

