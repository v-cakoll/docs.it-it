---
title: -fullpaths (opzioni del compilatore C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- /fullpaths
dev_langs:
- CSharp
helpviewer_keywords:
- /fullpaths compiler option [C#]
- absolute paths [C#]
- fullpaths compiler option [C#]
- full paths [C#]
- -fullpaths compiler option [C#]
ms.assetid: d2a5f857-cbb2-430b-879c-d648aaf0b8c4
caps.latest.revision: 10
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
ms.openlocfilehash: abd78253c44ae1c90241b2ff2bd236513a846384
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="fullpaths-c-compiler-options"></a><span data-ttu-id="eae45-102">/fullpaths (opzioni del compilatore C#)</span><span class="sxs-lookup"><span data-stu-id="eae45-102">/fullpaths (C# Compiler Options)</span></span>
<span data-ttu-id="eae45-103">L'opzione **/fullpaths** fa in modo che il compilatore specifichi il percorso completo del file quando vengono elencati gli avvisi e gli errori di compilazione.</span><span class="sxs-lookup"><span data-stu-id="eae45-103">The **/fullpaths** option causes the compiler to specify the full path to the file when listing compilation errors and warnings.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eae45-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="eae45-104">Syntax</span></span>  
  
```console  
/fullpaths  
```  
  
## <a name="remarks"></a><span data-ttu-id="eae45-105">Note</span><span class="sxs-lookup"><span data-stu-id="eae45-105">Remarks</span></span>  
 <span data-ttu-id="eae45-106">Per impostazione predefinita, per gli errori e gli avvisi generati dalla compilazione viene specificato il nome del file in cui si è verificato un errore.</span><span class="sxs-lookup"><span data-stu-id="eae45-106">By default, errors and warnings that result from compilation specify the name of the file in which an error was found.</span></span> <span data-ttu-id="eae45-107">L'opzione **/fullpaths** fa in modo che il compilatore specifichi il percorso completo del file.</span><span class="sxs-lookup"><span data-stu-id="eae45-107">The **/fullpaths** option causes the compiler to specify the full path to the file.</span></span>  
  
 <span data-ttu-id="eae45-108">Questa opzione del compilatore non è disponibile in Visual Studio e non può essere modificata a livello di codice.</span><span class="sxs-lookup"><span data-stu-id="eae45-108">This compiler option is unavailable in Visual Studio and cannot be changed programmatically.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eae45-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="eae45-109">See Also</span></span>  
 [<span data-ttu-id="eae45-110">Opzioni del compilatore C#</span><span class="sxs-lookup"><span data-stu-id="eae45-110">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)

