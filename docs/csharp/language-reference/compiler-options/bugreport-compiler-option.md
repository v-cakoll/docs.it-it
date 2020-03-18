---
title: -bugreport (opzioni del compilatore C#s)
ms.date: 07/20/2015
f1_keywords:
- /bugreport
helpviewer_keywords:
- /bugreport compiler option [C#]
- -bugreport compiler option [C#]
- bugreport compiler option [C#]
ms.assetid: f39665e3-4f6f-4357-88a2-3274c7bec0c1
ms.openlocfilehash: 0989678be070910c410d71717fe66679e1b70557
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "69603075"
---
# <a name="-bugreport-c-compiler-options"></a><span data-ttu-id="5278c-102">-bugreport (opzioni del compilatore C#s)</span><span class="sxs-lookup"><span data-stu-id="5278c-102">-bugreport (C# Compiler Options)</span></span>
<span data-ttu-id="5278c-103">Specifica che le informazioni di debug devono essere inserite in un file per analisi successive.</span><span class="sxs-lookup"><span data-stu-id="5278c-103">Specifies that debug information should be placed in a file for later analysis.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5278c-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="5278c-104">Syntax</span></span>  
  
```console  
-bugreport:file  
```  
  
## <a name="arguments"></a><span data-ttu-id="5278c-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="5278c-105">Arguments</span></span>  
 `file`  
 <span data-ttu-id="5278c-106">Nome del file in cui si vuole inserire il report sui bug.</span><span class="sxs-lookup"><span data-stu-id="5278c-106">The name of the file that you want to contain your bug report.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5278c-107">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="5278c-107">Remarks</span></span>  
 <span data-ttu-id="5278c-108">L'opzione **-bugreport** specifica che le seguenti `file`informazioni devono essere inserite in :</span><span class="sxs-lookup"><span data-stu-id="5278c-108">The **-bugreport** option specifies that the following information should be placed in `file`:</span></span>  
  
- <span data-ttu-id="5278c-109">Una copia di tutti i file di codice sorgente nella compilazione.</span><span class="sxs-lookup"><span data-stu-id="5278c-109">A copy of all source code files in the compilation.</span></span>  
  
- <span data-ttu-id="5278c-110">Un elenco delle opzioni del compilatore usate nella compilazione.</span><span class="sxs-lookup"><span data-stu-id="5278c-110">A listing of the compiler options used in the compilation.</span></span>  
  
- <span data-ttu-id="5278c-111">Informazioni sulla versione per il compilatore, il runtime e il sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="5278c-111">Version information about your compiler, run time, and operating system.</span></span>  
  
- <span data-ttu-id="5278c-112">Assembly e moduli di riferimento, salvati come cifre esadecimali, ad eccezione degli assembly forniti con .NET Framework e SDK.</span><span class="sxs-lookup"><span data-stu-id="5278c-112">Referenced assemblies and modules, saved as hexadecimal digits, except assemblies that ship with the .NET Framework and SDK.</span></span>  
  
- <span data-ttu-id="5278c-113">L'eventuale output del compilatore.</span><span class="sxs-lookup"><span data-stu-id="5278c-113">Compiler output, if any.</span></span>  
  
- <span data-ttu-id="5278c-114">Una descrizione del problema, che verrà richiesta.</span><span class="sxs-lookup"><span data-stu-id="5278c-114">A description of the problem, which you will be prompted for.</span></span>  
  
- <span data-ttu-id="5278c-115">Una descrizione del modo in cui si può risolvere il problema, che verrà richiesta.</span><span class="sxs-lookup"><span data-stu-id="5278c-115">A description of how you think the problem should be fixed, which you will be prompted for.</span></span>  
  
 <span data-ttu-id="5278c-116">Se questa opzione viene utilizzata con **-errorreport:prompt** o **-errorreport:send**, le informazioni contenute nel file verranno inviate a Microsoft Corporation.</span><span class="sxs-lookup"><span data-stu-id="5278c-116">If this option is used with **-errorreport:prompt** or **-errorreport:send**, the information in the file will be sent to Microsoft Corporation.</span></span>  
  
 <span data-ttu-id="5278c-117">Dato che una copia di tutti i file di codice sorgente verrà inserita in `file`, potrebbe essere utile riprodurre il sospetto difetto del codice nel programma più breve possibile.</span><span class="sxs-lookup"><span data-stu-id="5278c-117">Because a copy of all source code files will be placed in `file`, you might want to reproduce the suspected code defect in the shortest possible program.</span></span>  
  
 <span data-ttu-id="5278c-118">Questa opzione del compilatore non è disponibile in Visual Studio e non può essere modificata a livello di codice.</span><span class="sxs-lookup"><span data-stu-id="5278c-118">This compiler option is unavailable in Visual Studio and cannot be changed programmatically.</span></span>  
  
 <span data-ttu-id="5278c-119">Si noti che contenuto del file generato espone il codice sorgente e ciò potrebbe causare la divulgazione accidentale di informazioni.</span><span class="sxs-lookup"><span data-stu-id="5278c-119">Notice that contents of the generated file expose source code that could result in inadvertent information disclosure.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5278c-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5278c-120">See also</span></span>

- [<span data-ttu-id="5278c-121">Opzioni del compilatore C</span><span class="sxs-lookup"><span data-stu-id="5278c-121">C# Compiler Options</span></span>](./index.md)
- [<span data-ttu-id="5278c-122">-errorreport (opzioni del compilatore C</span><span class="sxs-lookup"><span data-stu-id="5278c-122">-errorreport (C# Compiler Options)</span></span>](./errorreport-compiler-option.md)
- [<span data-ttu-id="5278c-123">Gestione delle proprietà di progetti e soluzioni</span><span class="sxs-lookup"><span data-stu-id="5278c-123">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
