---
title: -nowin32manifest (opzioni del compilatore C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- /nowin32manifest
dev_langs:
- CSharp
helpviewer_keywords:
- nowin32manifest compiler option [C#]
- -nowin32manifest compiler option [C#]
- /nowin32manifest compiler option [C#]
ms.assetid: 6f06365b-b87b-46a2-b187-b3bfeaf4862d
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
ms.openlocfilehash: 8314fd661ccce968238b480b54847abf7cbece74
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="nowin32manifest-c-compiler-options"></a>/nowin32manifest (opzioni del compilatore C#)
Usare l'opzione **/nowin32manifest** per indicare al compilatore di non incorporare un manifesto dell'applicazione nel file eseguibile.  
  
## <a name="syntax"></a>Sintassi  
  
```console  
/nowin32manifest  
```  
  
## <a name="remarks"></a>Note  
 Quando viene usata questa opzione, l'applicazione è soggetta a virtualizzazione in Windows Vista a meno che non venga specificato un manifesto dell'applicazione in un file di risorsa Win32 file o durante una istruzione di compilazione successiva.  
  
 In Visual Studio impostare l'opzione nella **pagina delle proprietà dell'applicazione** selezionando l'opzione **Crea applicazione senza manifesto** nell'elenco a discesa **Manifesto**. Per altre informazioni, vedere [Pagina Applicazione, Creazione progetti (C#)](/visualstudio/ide/reference/application-page-project-designer-csharp).  
  
 Per altre informazioni sulla creazione di manifesti, vedere [/win32manifest (opzioni del compilatore C#)](../../../csharp/language-reference/compiler-options/win32manifest-compiler-option.md).  
  
## <a name="see-also"></a>Vedere anche  
 [C# Compiler Options](../../../csharp/language-reference/compiler-options/index.md)  (Opzioni del compilatore C#)  
 [Gestione delle proprietà di progetti e soluzioni](/visualstudio/ide/managing-project-and-solution-properties)

