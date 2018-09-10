---
title: -recurse (opzioni del compilatore C#)
ms.date: 07/20/2015
f1_keywords:
- /recurse
helpviewer_keywords:
- /recurse compiler option [C#]
- recurse compiler option [C#]
- -recurse compiler option [C#]
ms.assetid: 4e8212e5-04e3-45b1-8a42-41bc50e683b0
ms.openlocfilehash: 1fc5591cb73164e15384eb4407a6e61e903eedbb
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2018
ms.locfileid: "43529897"
---
# <a name="-recurse-c-compiler-options"></a><span data-ttu-id="a9d91-102">-recurse (opzioni del compilatore C#)</span><span class="sxs-lookup"><span data-stu-id="a9d91-102">-recurse (C# Compiler Options)</span></span>
<span data-ttu-id="a9d91-103">L'opzione -recurse consente di compilare i file del codice sorgente in tutte le directory figlio della directory specificata (dir) o della directory del progetto.</span><span class="sxs-lookup"><span data-stu-id="a9d91-103">The -recurse option enables you to compile source code files in all child directories of either the specified directory (dir) or of the project directory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a9d91-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a9d91-104">Syntax</span></span>  
  
```console  
-recurse:[dir\]file  
```  
  
## <a name="arguments"></a><span data-ttu-id="a9d91-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="a9d91-105">Arguments</span></span>  
 <span data-ttu-id="a9d91-106">`dir` (facoltativo)</span><span class="sxs-lookup"><span data-stu-id="a9d91-106">`dir` (optional)</span></span>  
 <span data-ttu-id="a9d91-107">La directory in cui si vuole che abbia inizio la ricerca.</span><span class="sxs-lookup"><span data-stu-id="a9d91-107">The directory in which you want the search to begin.</span></span> <span data-ttu-id="a9d91-108">Se non viene specificata alcuna directory, la ricerca avrà inizio nella directory del progetto.</span><span class="sxs-lookup"><span data-stu-id="a9d91-108">If this is not specified, the search begins in the project directory.</span></span>  
  
 `file`  
 <span data-ttu-id="a9d91-109">I file da cercare.</span><span class="sxs-lookup"><span data-stu-id="a9d91-109">The file(s) to search for.</span></span> <span data-ttu-id="a9d91-110">È consentito l'utilizzo di caratteri jolly.</span><span class="sxs-lookup"><span data-stu-id="a9d91-110">Wildcard characters are allowed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a9d91-111">Note</span><span class="sxs-lookup"><span data-stu-id="a9d91-111">Remarks</span></span>  
 <span data-ttu-id="a9d91-112">L'opzione **-recurse** consente di compilare file di codice sorgente in tutte le directory figlio della directory specificata (`dir`) o della directory del progetto.</span><span class="sxs-lookup"><span data-stu-id="a9d91-112">The **-recurse** option lets you compile source code files in all child directories of either the specified directory (`dir`) or of the project directory.</span></span>  
  
 <span data-ttu-id="a9d91-113">È possibile usare caratteri jolly in un nome file per compilare tutti i file corrispondenti della directory del progetto senza usare **-recurse**.</span><span class="sxs-lookup"><span data-stu-id="a9d91-113">You can use wildcards in a file name to compile all matching files in the project directory without using **-recurse**.</span></span>  
  
 <span data-ttu-id="a9d91-114">Questa opzione del compilatore non è disponibile in Visual Studio e non può essere modificata a livello di codice.</span><span class="sxs-lookup"><span data-stu-id="a9d91-114">This compiler option is unavailable in Visual Studio and cannot be changed programmatically.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a9d91-115">Esempio</span><span class="sxs-lookup"><span data-stu-id="a9d91-115">Example</span></span>  
 <span data-ttu-id="a9d91-116">Compila tutti i file C# della directory corrente:</span><span class="sxs-lookup"><span data-stu-id="a9d91-116">Compiles all C# files in the current directory:</span></span>  
  
```console  
csc *.cs  
```  
  
 <span data-ttu-id="a9d91-117">Compila tutti i file C# della directory dir1\dir2 e di eventuali sottodirectory e genera dir2.dll:</span><span class="sxs-lookup"><span data-stu-id="a9d91-117">Compiles all of the C# files in the dir1\dir2 directory and any directories below it and generates dir2.dll:</span></span>  
  
```console  
csc -target:library -out:dir2.dll -recurse:dir1\dir2\*.cs  
```  
  
## <a name="see-also"></a><span data-ttu-id="a9d91-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a9d91-118">See Also</span></span>  

- [<span data-ttu-id="a9d91-119">Opzioni del compilatore C#</span><span class="sxs-lookup"><span data-stu-id="a9d91-119">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)  
- [<span data-ttu-id="a9d91-120">Gestione delle proprietà di progetti e soluzioni</span><span class="sxs-lookup"><span data-stu-id="a9d91-120">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
