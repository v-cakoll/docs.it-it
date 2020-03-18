---
title: -codepage (opzioni del compilatore C#)
ms.date: 07/20/2015
f1_keywords:
- /codepage
helpviewer_keywords:
- /codepage compiler option [C#]
- codepage compiler option [C#]
- -codepage compiler option [C#]
ms.assetid: 75942989-b69a-4308-90a0-840c73d2c478
ms.openlocfilehash: 3352e7fc446ace391540360a3b6b36d604ca5f13
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "79173757"
---
# <a name="-codepage-c-compiler-options"></a><span data-ttu-id="1d79d-102">-codepage (opzioni del compilatore C#)</span><span class="sxs-lookup"><span data-stu-id="1d79d-102">-codepage (C# Compiler Options)</span></span>
<span data-ttu-id="1d79d-103">Questa opzione specifica la tabella codici da usare durante la compilazione, se la pagina richiesta non è la tabella codici predefinita corrente per il sistema.</span><span class="sxs-lookup"><span data-stu-id="1d79d-103">This option specifies which codepage to use during compilation if the required page is not the current default codepage for the system.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1d79d-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1d79d-104">Syntax</span></span>  
  
```console  
-codepage:id  
```  
  
## <a name="arguments"></a><span data-ttu-id="1d79d-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="1d79d-105">Arguments</span></span>  
 `id`  
 <span data-ttu-id="1d79d-106">ID della tabella codici da usare per tutti i file di codice sorgente nella compilazione.</span><span class="sxs-lookup"><span data-stu-id="1d79d-106">The id of the code page to use for all source code files in the compilation.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1d79d-107">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="1d79d-107">Remarks</span></span>  
 <span data-ttu-id="1d79d-108">Il compilatore tenterà innanzitutto di interpretare tutti i file di origine come UTF-8.</span><span class="sxs-lookup"><span data-stu-id="1d79d-108">The compiler will first attempt to interpret all source files as UTF-8.</span></span> <span data-ttu-id="1d79d-109">Se i file del codice sorgente sono codificati con una codifica diversa da UTF-8 e usano caratteri diversi dai caratteri ASCII a 7 bit, usare l'opzione **-codepage** per specificare la tabella codici da usare.</span><span class="sxs-lookup"><span data-stu-id="1d79d-109">If your source code files are in an encoding other than UTF-8 and use characters other than 7-bit ASCII characters, use the **-codepage** option to specify which code page should be used.</span></span> <span data-ttu-id="1d79d-110">**-codepage** si applica a tutti i file di codice sorgente nella compilazione.</span><span class="sxs-lookup"><span data-stu-id="1d79d-110">**-codepage** applies to all source code files in your compilation.</span></span>  

 <span data-ttu-id="1d79d-111">Per informazioni su come individuare le tabelle codici supportate nel sistema, vedere [GetCPInfo](/windows/desktop/api/winnls/nf-winnls-getcpinfo).</span><span class="sxs-lookup"><span data-stu-id="1d79d-111">See [GetCPInfo](/windows/desktop/api/winnls/nf-winnls-getcpinfo) for information on how to find which code pages are supported on your system.</span></span>  
  
 <span data-ttu-id="1d79d-112">Questa opzione del compilatore non è disponibile in Visual Studio e non può essere modificata a livello di codice.</span><span class="sxs-lookup"><span data-stu-id="1d79d-112">This compiler option is unavailable in Visual Studio and cannot be changed programmatically.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1d79d-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1d79d-113">See also</span></span>

- [<span data-ttu-id="1d79d-114">Opzioni del compilatore C</span><span class="sxs-lookup"><span data-stu-id="1d79d-114">C# Compiler Options</span></span>](./index.md)
- [<span data-ttu-id="1d79d-115">Gestione delle proprietà di progetti e soluzioni</span><span class="sxs-lookup"><span data-stu-id="1d79d-115">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
