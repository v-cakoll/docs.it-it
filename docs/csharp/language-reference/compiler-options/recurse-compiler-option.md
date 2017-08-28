---
title: -recurse (opzioni del compilatore C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- /recurse
dev_langs:
- CSharp
helpviewer_keywords:
- /recurse compiler option [C#]
- recurse compiler option [C#]
- -recurse compiler option [C#]
ms.assetid: 4e8212e5-04e3-45b1-8a42-41bc50e683b0
caps.latest.revision: 12
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
ms.openlocfilehash: 99664f8b32f5f9e5bf491c5bfde2c1649de42dd9
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="recurse-c-compiler-options"></a>/recurse (opzioni del compilatore C#)
L'opzione /recurse consente di compilare il file di codice sorgente in tutte le directory figlio della directory specificata (dir) o della directory del progetto.  
  
## <a name="syntax"></a>Sintassi  
  
```console  
/recurse:[dir\]file  
```  
  
## <a name="arguments"></a>Argomenti  
 `dir` (facoltativo)  
 La directory in cui si vuole che abbia inizio la ricerca. Se non viene specificata alcuna directory, la ricerca avrà inizio nella directory del progetto.  
  
 `file`  
 I file da cercare. È consentito l'utilizzo di caratteri jolly.  
  
## <a name="remarks"></a>Note  
 L'opzione **/recurse** consente di compilare file di codice sorgente in tutte le directory figlio della directory specificata (`dir`) o della directory del progetto.  
  
 È possibile usare caratteri jolly in un nome file per compilare tutti i file corrispondenti della directory del progetto senza usare **/recurse**.  
  
 Questa opzione del compilatore non è disponibile in Visual Studio e non può essere modificata a livello di codice.  
  
## <a name="example"></a>Esempio  
 Compila tutti i file C# della directory corrente:  
  
```console  
csc *.cs  
```  
  
 Compila tutti i file C# della directory dir1\dir2 e di eventuali sottodirectory e genera dir2.dll:  
  
```console  
csc /target:library /out:dir2.dll /recurse:dir1\dir2\*.cs  
```  
  
## <a name="see-also"></a>Vedere anche  
 [C# Compiler Options](../../../csharp/language-reference/compiler-options/index.md)  (Opzioni del compilatore C#)  
 [Gestione delle proprietà di progetti e soluzioni](/visualstudio/ide/managing-project-and-solution-properties)

