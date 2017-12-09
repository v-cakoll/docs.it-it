---
title: -codepage (opzioni del compilatore C#)
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords: /codepage
helpviewer_keywords:
- /codepage compiler option [C#]
- codepage compiler option [C#]
- -codepage compiler option [C#]
ms.assetid: 75942989-b69a-4308-90a0-840c73d2c478
caps.latest.revision: "15"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 1e17622256ca6a0344797ba16e007ba6feb8f873
ms.sourcegitcommit: 401c4427a3ec0d1263543033b3084039278509dc
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/06/2017
---
# <a name="codepage-c-compiler-options"></a><span data-ttu-id="f8a4b-102">/codepage (opzioni del compilatore C#)</span><span class="sxs-lookup"><span data-stu-id="f8a4b-102">/codepage (C# Compiler Options)</span></span>
<span data-ttu-id="f8a4b-103">Questa opzione specifica la tabella codici da usare durante la compilazione, se la pagina richiesta non è la tabella codici predefinita corrente per il sistema.</span><span class="sxs-lookup"><span data-stu-id="f8a4b-103">This option specifies which codepage to use during compilation if the required page is not the current default codepage for the system.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f8a4b-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f8a4b-104">Syntax</span></span>  
  
```console  
/codepage:id  
```  
  
## <a name="arguments"></a><span data-ttu-id="f8a4b-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="f8a4b-105">Arguments</span></span>  
 `id`  
 <span data-ttu-id="f8a4b-106">ID della tabella codici da usare per tutti i file di codice sorgente nella compilazione.</span><span class="sxs-lookup"><span data-stu-id="f8a4b-106">The id of the code page to use for all source code files in the compilation.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f8a4b-107">Note</span><span class="sxs-lookup"><span data-stu-id="f8a4b-107">Remarks</span></span>  
 <span data-ttu-id="f8a4b-108">Se si compilano uno o più file di codice sorgente che non sono stati creati per usare la tabella codici predefinita nel computer in uso, è possibile usare l'opzione **/codepage** per specificare la tabella codici da usare.</span><span class="sxs-lookup"><span data-stu-id="f8a4b-108">If you compile one or more source code files that were not created to use the default code page on your computer, you can use the **/codepage** option to specify which code page should be used.</span></span> <span data-ttu-id="f8a4b-109">**/codepage** si applica a tutti i file di codice sorgente nella compilazione.</span><span class="sxs-lookup"><span data-stu-id="f8a4b-109">**/codepage** applies to all source code files in your compilation.</span></span>  
  
 <span data-ttu-id="f8a4b-110">Se i file di codice sorgente sono stati creati con la stessa tabella codici attiva nel computer in uso o se i file di codice sorgente sono stati creati con UNICODE o UTF-8, non sarà necessario usare **/codepage**.</span><span class="sxs-lookup"><span data-stu-id="f8a4b-110">If the source code files were created with the same codepage that is in effect on your computer or if the source code files were created with UNICODE or UTF-8, you need not use **/codepage**.</span></span>  
  
 <span data-ttu-id="f8a4b-111">Per informazioni su come individuare le tabelle codici supportate nel sistema, vedere [GetCPInfo](https://msdn.microsoft.com/library/dd318078(VS.85).aspx).</span><span class="sxs-lookup"><span data-stu-id="f8a4b-111">See [GetCPInfo](https://msdn.microsoft.com/library/dd318078(VS.85).aspx) for information on how to find which code pages are supported on your system.</span></span>  
  
 <span data-ttu-id="f8a4b-112">Questa opzione del compilatore non è disponibile in Visual Studio e non può essere modificata a livello di codice.</span><span class="sxs-lookup"><span data-stu-id="f8a4b-112">This compiler option is unavailable in Visual Studio and cannot be changed programmatically.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f8a4b-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f8a4b-113">See Also</span></span>  
 [<span data-ttu-id="f8a4b-114">Opzioni del compilatore C#</span><span class="sxs-lookup"><span data-stu-id="f8a4b-114">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)  
 [<span data-ttu-id="f8a4b-115">Gestione delle proprietà di progetti e soluzioni</span><span class="sxs-lookup"><span data-stu-id="f8a4b-115">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
