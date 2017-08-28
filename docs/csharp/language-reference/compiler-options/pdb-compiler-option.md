---
title: -pdb (opzioni del compilatore C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- /pdb
dev_langs:
- CSharp
helpviewer_keywords:
- -pdb compiler option [C#]
- pdb compiler option [C#]
- /pdb compiler option [C#]
ms.assetid: e9d0f96a-5b75-45d6-9765-92538dd5f823
caps.latest.revision: 8
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
ms.openlocfilehash: 7c72c12347a9096aeed063b84310356cb07b49c3
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="pdb-c-compiler-options"></a>/pdb (opzioni del compilatore C#)
L'opzione del compilatore **/pdb** consente di specificare il nome e il percorso del file di simboli di debug.  
  
## <a name="syntax"></a>Sintassi  
  
```console  
/pdb:filename  
```  
  
## <a name="arguments"></a>Argomenti  
 `filename`  
 Nome e percorso del file di simboli di debug.  
  
## <a name="remarks"></a>Note  
 Quando si specifica [/debug (opzioni del compilatore C#)](../../../csharp/language-reference/compiler-options/debug-compiler-option.md), il compilatore crea nella stessa directory in cui verrà creato il file di output (con estensione exe o dll) un file con estensione pdb il cui nome è identico a quello del file di output.  
  
 **/PDB** consente di specificare un nome e un percorso non predefiniti per il file con estensione pdb.  
  
 Questa opzione del compilatore non può essere impostata nell'ambiente di sviluppo di Visual Studio, né modificata a livello di codice.  
  
## <a name="example"></a>Esempio  
 Compilare `t.cs` e creare un file con estensione pdb denominato tt.pdb:  
  
```console  
csc /debug /pdb:tt t.cs  
```  
  
## <a name="see-also"></a>Vedere anche  
 [C# Compiler Options](../../../csharp/language-reference/compiler-options/index.md)  (Opzioni del compilatore C#)  
 [Gestione delle proprietà di progetti e soluzioni](/visualstudio/ide/managing-project-and-solution-properties)

