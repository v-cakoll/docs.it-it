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
ms.openlocfilehash: f25455fac84903f9c39861e1f6863f6b2f6928f3
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64587381"
---
# <a name="-bugreport-c-compiler-options"></a><span data-ttu-id="6c3ac-102">-bugreport (opzioni del compilatore C#s)</span><span class="sxs-lookup"><span data-stu-id="6c3ac-102">-bugreport (C# Compiler Options)</span></span>
<span data-ttu-id="6c3ac-103">Specifica che le informazioni di debug devono essere inserite in un file per analisi successive.</span><span class="sxs-lookup"><span data-stu-id="6c3ac-103">Specifies that debug information should be placed in a file for later analysis.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6c3ac-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="6c3ac-104">Syntax</span></span>  
  
```console  
-bugreport:file  
```  
  
## <a name="arguments"></a><span data-ttu-id="6c3ac-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="6c3ac-105">Arguments</span></span>  
 `file`  
 <span data-ttu-id="6c3ac-106">Nome del file in cui si vuole inserire il report sui bug.</span><span class="sxs-lookup"><span data-stu-id="6c3ac-106">The name of the file that you want to contain your bug report.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6c3ac-107">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="6c3ac-107">Remarks</span></span>  
 <span data-ttu-id="6c3ac-108">L'opzione **-bugreport** specifica che in `file` devono essere inserite le informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="6c3ac-108">The **-bugreport** option specifies that the following information should be placed in `file`:</span></span>  
  
- <span data-ttu-id="6c3ac-109">Una copia di tutti i file di codice sorgente nella compilazione.</span><span class="sxs-lookup"><span data-stu-id="6c3ac-109">A copy of all source code files in the compilation.</span></span>  
  
- <span data-ttu-id="6c3ac-110">Un elenco delle opzioni del compilatore usate nella compilazione.</span><span class="sxs-lookup"><span data-stu-id="6c3ac-110">A listing of the compiler options used in the compilation.</span></span>  
  
- <span data-ttu-id="6c3ac-111">Informazioni sulla versione per il compilatore, il runtime e il sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="6c3ac-111">Version information about your compiler, run time, and operating system.</span></span>  
  
- <span data-ttu-id="6c3ac-112">Assembly e moduli di riferimento, salvati come cifre esadecimali, ad eccezione degli assembly forniti con .NET Framework e SDK.</span><span class="sxs-lookup"><span data-stu-id="6c3ac-112">Referenced assemblies and modules, saved as hexadecimal digits, except assemblies that ship with the .NET Framework and SDK.</span></span>  
  
- <span data-ttu-id="6c3ac-113">L'eventuale output del compilatore.</span><span class="sxs-lookup"><span data-stu-id="6c3ac-113">Compiler output, if any.</span></span>  
  
- <span data-ttu-id="6c3ac-114">Una descrizione del problema, che verrà richiesta.</span><span class="sxs-lookup"><span data-stu-id="6c3ac-114">A description of the problem, which you will be prompted for.</span></span>  
  
- <span data-ttu-id="6c3ac-115">Una descrizione del modo in cui si può risolvere il problema, che verrà richiesta.</span><span class="sxs-lookup"><span data-stu-id="6c3ac-115">A description of how you think the problem should be fixed, which you will be prompted for.</span></span>  
  
 <span data-ttu-id="6c3ac-116">Se questa opzione viene usata con **-errorreport:prompt** o **-errorreport:send**, le informazioni nel file verranno inviate a Microsoft Corporation.</span><span class="sxs-lookup"><span data-stu-id="6c3ac-116">If this option is used with **-errorreport:prompt** or **-errorreport:send**, the information in the file will be sent to Microsoft Corporation.</span></span>  
  
 <span data-ttu-id="6c3ac-117">Dato che una copia di tutti i file di codice sorgente verrà inserita in `file`, potrebbe essere utile riprodurre il sospetto difetto del codice nel programma più breve possibile.</span><span class="sxs-lookup"><span data-stu-id="6c3ac-117">Because a copy of all source code files will be placed in `file`, you might want to reproduce the suspected code defect in the shortest possible program.</span></span>  
  
 <span data-ttu-id="6c3ac-118">Questa opzione del compilatore non è disponibile in Visual Studio e non può essere modificata a livello di codice.</span><span class="sxs-lookup"><span data-stu-id="6c3ac-118">This compiler option is unavailable in Visual Studio and cannot be changed programmatically.</span></span>  
  
 <span data-ttu-id="6c3ac-119">Si noti che contenuto del file generato espone il codice sorgente e ciò potrebbe causare la divulgazione accidentale di informazioni.</span><span class="sxs-lookup"><span data-stu-id="6c3ac-119">Notice that contents of the generated file expose source code that could result in inadvertent information disclosure.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6c3ac-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6c3ac-120">See also</span></span>

- [<span data-ttu-id="6c3ac-121">Opzioni del compilatore C#</span><span class="sxs-lookup"><span data-stu-id="6c3ac-121">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)
- [<span data-ttu-id="6c3ac-122">-errorreport (opzioni del compilatore C#)</span><span class="sxs-lookup"><span data-stu-id="6c3ac-122">-errorreport (C# Compiler Options)</span></span>](../../../csharp/language-reference/compiler-options/errorreport-compiler-option.md)
- [<span data-ttu-id="6c3ac-123">Gestione delle proprietà di progetti e soluzioni</span><span class="sxs-lookup"><span data-stu-id="6c3ac-123">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
