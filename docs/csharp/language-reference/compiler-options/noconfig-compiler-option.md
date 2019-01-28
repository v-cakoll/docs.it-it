---
title: -noconfig (opzioni del compilatore C#)
ms.date: 07/20/2015
f1_keywords:
- /noconfig
helpviewer_keywords:
- /noconfig compiler option [C#]
- csc.rsp
- -noconfig compiler option [C#]
- noconfig compiler option [C#]
ms.assetid: cd26967e-e494-4c8c-b5c9-af13b2f78b2e
ms.openlocfilehash: 8d28ef1334df847865721783fa98aaa9d8c576be
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54528576"
---
# <a name="-noconfig-c-compiler-options"></a><span data-ttu-id="957ec-102">-noconfig (opzioni del compilatore C#)</span><span class="sxs-lookup"><span data-stu-id="957ec-102">-noconfig (C# Compiler Options)</span></span>
<span data-ttu-id="957ec-103">L'opzione **-noconfig** indica al compilatore di non eseguire la compilazione con il file csc.rsp, caricato e reso disponibile dalla stessa directory in cui si trova il file csc.exe.</span><span class="sxs-lookup"><span data-stu-id="957ec-103">The **-noconfig** option tells the compiler not to compile with the csc.rsp file, which is located in and loaded from the same directory as the csc.exe file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="957ec-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="957ec-104">Syntax</span></span>  
  
```console  
-noconfig  
```  
  
## <a name="remarks"></a><span data-ttu-id="957ec-105">Note</span><span class="sxs-lookup"><span data-stu-id="957ec-105">Remarks</span></span>  
 <span data-ttu-id="957ec-106">Il file csc.rsp fa riferimento a tutti gli assembly forniti con .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="957ec-106">The csc.rsp file references all the assemblies shipped with the .NET Framework.</span></span> <span data-ttu-id="957ec-107">I riferimenti effettivi inclusi nell'ambiente di sviluppo di Visual Studio .NET dipendono dal tipo di progetto.</span><span class="sxs-lookup"><span data-stu-id="957ec-107">The actual references that the Visual Studio .NET development environment includes depend on the project type.</span></span>  
  
 <span data-ttu-id="957ec-108">È possibile modificare il file csc.rsp e specificare altre opzioni del compilatore da includere in ogni compilazione eseguita dalla riga di comando usando il file csc.exe (ad eccezione dell'opzione **-noconfig**).</span><span class="sxs-lookup"><span data-stu-id="957ec-108">You can modify the csc.rsp file and specify additional compiler options that should be included in every compilation from the command line with csc.exe (except the **-noconfig** option).</span></span>  
  
 <span data-ttu-id="957ec-109">Le opzioni passate al comando **csc** verranno elaborate nel compilatore per ultime.</span><span class="sxs-lookup"><span data-stu-id="957ec-109">The compiler processes the options passed to the **csc** command last.</span></span> <span data-ttu-id="957ec-110">Le opzioni della riga di comando eseguiranno pertanto l'override delle impostazioni relative alle stesse opzioni nel file csc.rsp.</span><span class="sxs-lookup"><span data-stu-id="957ec-110">Therefore, any option on the command line overrides the setting of the same option in the csc.rsp file.</span></span>  
  
 <span data-ttu-id="957ec-111">Se non si vuole che il compilatore cerchi e usi le impostazioni del file csc.rsp, specificare **-noconfig**.</span><span class="sxs-lookup"><span data-stu-id="957ec-111">If you do not want the compiler to look for and use the settings in the csc.rsp file, specify **-noconfig**.</span></span>  
  
 <span data-ttu-id="957ec-112">Questa opzione del compilatore non è disponibile in Visual Studio e non può essere modificata a livello di codice.</span><span class="sxs-lookup"><span data-stu-id="957ec-112">This compiler option is unavailable in Visual Studio and cannot be changed programmatically.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="957ec-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="957ec-113">See also</span></span>

- [<span data-ttu-id="957ec-114">Opzioni del compilatore C#</span><span class="sxs-lookup"><span data-stu-id="957ec-114">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)
- [<span data-ttu-id="957ec-115">Gestione delle proprietà di progetti e soluzioni</span><span class="sxs-lookup"><span data-stu-id="957ec-115">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
