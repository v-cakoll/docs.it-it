---
title: -nowin32manifest (opzioni del compilatore C#)
ms.date: 07/20/2015
f1_keywords:
- /nowin32manifest
helpviewer_keywords:
- nowin32manifest compiler option [C#]
- -nowin32manifest compiler option [C#]
- /nowin32manifest compiler option [C#]
ms.assetid: 6f06365b-b87b-46a2-b187-b3bfeaf4862d
ms.openlocfilehash: 3ab52d541c169850f6ae7ba7e7cfded290f890e7
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/02/2018
ms.locfileid: "43420619"
---
# <a name="-nowin32manifest-c-compiler-options"></a>-nowin32manifest (opzioni del compilatore C#)
Usare l'opzione **-nowin32manifest** per indicare al compilatore di non incorporare un manifesto dell'applicazione nel file eseguibile.  
  
## <a name="syntax"></a>Sintassi  
  
```console  
-nowin32manifest  
```  
  
## <a name="remarks"></a>Note  
 Quando viene usata questa opzione, l'applicazione è soggetta a virtualizzazione in Windows Vista a meno che non venga specificato un manifesto dell'applicazione in un file di risorsa Win32 file o durante una istruzione di compilazione successiva.  
  
 In Visual Studio impostare l'opzione nella **pagina delle proprietà dell'applicazione** selezionando l'opzione **Crea applicazione senza manifesto** nell'elenco a discesa **Manifesto**. Per altre informazioni, vedere [Pagina Applicazione, Creazione progetti (C#)](/visualstudio/ide/reference/application-page-project-designer-csharp).  
  
 Per altre informazioni sulla creazione di manifesti, vedere [/win32manifest (opzioni del compilatore C#)](../../../csharp/language-reference/compiler-options/win32manifest-compiler-option.md).  
  
## <a name="see-also"></a>Vedere anche  

- [Opzioni del compilatore C#](../../../csharp/language-reference/compiler-options/index.md)  
- [Gestione delle proprietà di progetti e soluzioni](/visualstudio/ide/managing-project-and-solution-properties)
