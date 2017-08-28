---
title: -unsafe (opzioni del compilatore C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- /unsafe
dev_langs:
- CSharp
helpviewer_keywords:
- -unsafe compiler option [C#]
- unsafe compiler option [C#]
- /unsafe compiler option [C#]
ms.assetid: fdb77ed9-da03-45bd-bb7f-250704da1bcc
caps.latest.revision: 19
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
ms.openlocfilehash: 8f285af57d6a06d38d20b2c28e4a637fbc3ecf2c
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="unsafe-c-compiler-options"></a>/unsafe (opzioni del compilatore C#)
L'opzione del compilatore **/unsafe** consente la compilazione del codice che usa la parola chiave [unsafe](../../../csharp/language-reference/keywords/unsafe.md).  
  
## <a name="syntax"></a>Sintassi  
  
```console  
/unsafe  
```  
  
## <a name="remarks"></a>Note  
 Per altre informazioni sul codice unsafe, vedere [Codice unsafe e puntatori](../../../csharp/programming-guide/unsafe-code-pointers/index.md).  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Per impostare l'opzione del compilatore nell'ambiente di sviluppo di Visual Studio  
  
1.  Aprire la pagine **Proprietà** del progetto.  
  
2.  Fare clic sulla pagina della proprietà **Compilazione**.  
  
3.  Selezionare la casella di controllo **Consenti codice unsafe**.  
  
 Per informazioni su come impostare questa opzione del compilatore a livello di codice, vedere <xref:VSLangProj80.CSharpProjectConfigurationProperties3.AllowUnsafeBlocks%2A>.  
  
## <a name="example"></a>Esempio  
 Compilare `in.cs` per la modalità unsafe:  
  
```console  
csc /unsafe in.cs  
```  
  
## <a name="see-also"></a>Vedere anche  
 [C# Compiler Options](../../../csharp/language-reference/compiler-options/index.md)  (Opzioni del compilatore C#)  
 [Gestione delle proprietà di progetti e soluzioni](/visualstudio/ide/managing-project-and-solution-properties)

