---
title: -nostdlib (opzioni del compilatore C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- /nostdlib
dev_langs:
- CSharp
helpviewer_keywords:
- nostdlib compiler option [C#]
- -nostdlib compiler option [C#]
- /nostdlib compiler option [C#]
ms.assetid: ec197989-fa49-4725-a455-e06b551eb65f
caps.latest.revision: 18
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 1d500e2e55ab3117aa674e11d6cdd25703035879
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="nostdlib-c-compiler-options"></a>/nostdlib (opzioni del compilatore C#)
**/nostdlib** impedisce l'importazione di mscorlib.dll, che definisce l'intero spazio dei nomi System.  
  
## <a name="syntax"></a>Sintassi  
  
```console  
/nostdlib[+ | -]  
```  
  
## <a name="remarks"></a>Note  
 Usare questa opzione se si vuole definire o creare uno spazio dei nomi e oggetti System personalizzati.  
  
 Se non si specifica **/nostdlib**, mscorlib.dll verrà importata nel programma (equivale a specificare **/nostdlib-**). Specificare **/nostdlib** equivale a specificare **/nostdlib+**.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Per impostare l'opzione del compilatore nell'ambiente di sviluppo di Visual Studio  
  
1.  Aprire la pagina **Proprietà** del progetto.  
  
2.  Fare clic sulla pagina di proprietà **Compilazione** .  
  
3.  Fare clic su **Avanzate** .  
  
4.  Modificare la proprietà **Ometti riferimenti a libreria standard (mscorlib.dll)** .  
  
 Per informazioni su come impostare questa opzione del compilatore a livello di codice, vedere <xref:VSLangProj80.CSharpProjectConfigurationProperties3.NoStdLib%2A>.  
  
## <a name="see-also"></a>Vedere anche  
 [Opzioni del compilatore C#](../../../csharp/language-reference/compiler-options/index.md)

