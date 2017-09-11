---
title: -noconfig (opzioni del compilatore C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- /noconfig
dev_langs:
- CSharp
helpviewer_keywords:
- /noconfig compiler option [C#]
- csc.rsp
- -noconfig compiler option [C#]
- noconfig compiler option [C#]
ms.assetid: cd26967e-e494-4c8c-b5c9-af13b2f78b2e
caps.latest.revision: 11
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
ms.openlocfilehash: 594e972dc834ab74412e30a48428f850ae02b5ac
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="noconfig-c-compiler-options"></a><span data-ttu-id="e5651-102">/noconfig (opzioni del compilatore C#)</span><span class="sxs-lookup"><span data-stu-id="e5651-102">/noconfig (C# Compiler Options)</span></span>
<span data-ttu-id="e5651-103">L'opzione **/noconfig** indica al compilatore di non eseguire la compilazione con il file csc.rsp, caricato e reso disponibile dalla stessa directory in cui si trova il file csc.exe.</span><span class="sxs-lookup"><span data-stu-id="e5651-103">The **/noconfig** option tells the compiler not to compile with the csc.rsp file, which is located in and loaded from the same directory as the csc.exe file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e5651-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e5651-104">Syntax</span></span>  
  
```console  
/noconfig  
```  
  
## <a name="remarks"></a><span data-ttu-id="e5651-105">Note</span><span class="sxs-lookup"><span data-stu-id="e5651-105">Remarks</span></span>  
 <span data-ttu-id="e5651-106">Il file csc.rsp fa riferimento a tutti gli assembly forniti con .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="e5651-106">The csc.rsp file references all the assemblies shipped with the .NET Framework.</span></span> <span data-ttu-id="e5651-107">I riferimenti effettivi inclusi nell'ambiente di sviluppo di Visual Studio .NET dipendono dal tipo di progetto.</span><span class="sxs-lookup"><span data-stu-id="e5651-107">The actual references that the Visual Studio .NET development environment includes depend on the project type.</span></span>  
  
 <span data-ttu-id="e5651-108">È possibile modificare il file csc.rsp e specificare altre opzioni del compilatore da includere in ogni compilazione eseguita dalla riga di comando usando il file csc.exe (ad eccezione dell'opzione **/noconfig**).</span><span class="sxs-lookup"><span data-stu-id="e5651-108">You can modify the csc.rsp file and specify additional compiler options that should be included in every compilation from the command line with csc.exe (except the **/noconfig** option).</span></span>  
  
 <span data-ttu-id="e5651-109">Le opzioni passate al comando **csc** verranno elaborate nel compilatore per ultime.</span><span class="sxs-lookup"><span data-stu-id="e5651-109">The compiler processes the options passed to the **csc** command last.</span></span> <span data-ttu-id="e5651-110">Le opzioni della riga di comando eseguiranno pertanto l'override delle impostazioni relative alle stesse opzioni nel file csc.rsp.</span><span class="sxs-lookup"><span data-stu-id="e5651-110">Therefore, any option on the command line overrides the setting of the same option in the csc.rsp file.</span></span>  
  
 <span data-ttu-id="e5651-111">Se non si vuole che il compilatore cerchi e usi le impostazioni del file csc.rsp, specificare **/noconfig**.</span><span class="sxs-lookup"><span data-stu-id="e5651-111">If you do not want the compiler to look for and use the settings in the csc.rsp file, specify **/noconfig**.</span></span>  
  
 <span data-ttu-id="e5651-112">Questa opzione del compilatore non è disponibile in Visual Studio e non può essere modificata a livello di codice.</span><span class="sxs-lookup"><span data-stu-id="e5651-112">This compiler option is unavailable in Visual Studio and cannot be changed programmatically.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e5651-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e5651-113">See Also</span></span>  
 <span data-ttu-id="e5651-114">[C# Compiler Options](../../../csharp/language-reference/compiler-options/index.md)  (Opzioni del compilatore C#)</span><span class="sxs-lookup"><span data-stu-id="e5651-114">[C# Compiler Options](../../../csharp/language-reference/compiler-options/index.md) </span></span>  
 [<span data-ttu-id="e5651-115">Gestione delle proprietà di progetti e soluzioni</span><span class="sxs-lookup"><span data-stu-id="e5651-115">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)

