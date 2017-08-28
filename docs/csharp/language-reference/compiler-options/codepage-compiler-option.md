---
title: -codepage (opzioni del compilatore C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- /codepage
dev_langs:
- CSharp
helpviewer_keywords:
- /codepage compiler option [C#]
- codepage compiler option [C#]
- -codepage compiler option [C#]
ms.assetid: 75942989-b69a-4308-90a0-840c73d2c478
caps.latest.revision: 15
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
ms.openlocfilehash: b80f6fcf8891d2f0b921af01cc094f624d807aa1
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="codepage-c-compiler-options"></a>/codepage (opzioni del compilatore C#)
Questa opzione specifica la tabella codici da usare durante la compilazione, se la pagina richiesta non è la tabella codici predefinita corrente per il sistema.  
  
## <a name="syntax"></a>Sintassi  
  
```console  
/codepage:id  
```  
  
## <a name="arguments"></a>Argomenti  
 `id`  
 ID della tabella codici da usare per tutti i file di codice sorgente nella compilazione.  
  
## <a name="remarks"></a>Note  
 Se si compilano uno o più file di codice sorgente che non sono stati creati per usare la tabella codici predefinita nel computer in uso, è possibile usare l'opzione **/codepage** per specificare la tabella codici da usare. **/codepage** si applica a tutti i file di codice sorgente nella compilazione.  
  
 Se i file di codice sorgente sono stati creati con la stessa tabella codici attiva nel computer in uso o se i file di codice sorgente sono stati creati con UNICODE o UTF-8, non sarà necessario usare **/codepage**.  
  
 Per informazioni su come individuare le tabelle codici supportate nel sistema, vedere [GetCPInfo](http://go.microsoft.com/fwlink/?LinkId=148371).  
  
 Questa opzione del compilatore non è disponibile in Visual Studio e non può essere modificata a livello di codice.  
  
## <a name="see-also"></a>Vedere anche  
 [C# Compiler Options](../../../csharp/language-reference/compiler-options/index.md)  (Opzioni del compilatore C#)  
 [Gestione delle proprietà di progetti e soluzioni](/visualstudio/ide/managing-project-and-solution-properties)

