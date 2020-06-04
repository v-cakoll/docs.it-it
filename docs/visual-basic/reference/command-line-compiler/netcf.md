---
title: -netcf
ms.date: 03/13/2018
f1_keywords:
- /netcf
- -netcf
helpviewer_keywords:
- -netcf compiler option [Visual Basic]
- netcf compiler option [Visual Basic]
- /netcf compiler option [Visual Basic]
ms.assetid: db7cfa59-c315-401c-a59b-0daf355343d6
ms.openlocfilehash: 16fb6b3b63c848ea6c09cc18b0fcc488670f0926
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84397475"
---
# <a name="-netcf"></a><span data-ttu-id="7e21d-102">-netcf</span><span class="sxs-lookup"><span data-stu-id="7e21d-102">-netcf</span></span>

<span data-ttu-id="7e21d-103">Imposta il compilatore in modo che abbia come destinazione la .NET Compact Framework.</span><span class="sxs-lookup"><span data-stu-id="7e21d-103">Sets the compiler to target the .NET Compact Framework.</span></span>

## <a name="syntax"></a><span data-ttu-id="7e21d-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7e21d-104">Syntax</span></span>

```console
-netcf
```

## <a name="remarks"></a><span data-ttu-id="7e21d-105">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="7e21d-105">Remarks</span></span>

<span data-ttu-id="7e21d-106">L' `-netcf` opzione fa sì che il compilatore di Visual Basic faccia riferimento al .NET Compact Framework anziché al .NET Framework completo.</span><span class="sxs-lookup"><span data-stu-id="7e21d-106">The `-netcf` option causes the Visual Basic compiler to target the .NET Compact Framework rather than the full .NET Framework.</span></span> <span data-ttu-id="7e21d-107">La funzionalità del linguaggio presente solo nella .NET Framework completa è disabilitata.</span><span class="sxs-lookup"><span data-stu-id="7e21d-107">Language functionality that is present only in the full .NET Framework is disabled.</span></span>

<span data-ttu-id="7e21d-108">L' `-netcf` opzione è progettata per essere usata con [-sdkpath (](sdkpath.md).</span><span class="sxs-lookup"><span data-stu-id="7e21d-108">The `-netcf` option is designed to be used with [-sdkpath](sdkpath.md).</span></span> <span data-ttu-id="7e21d-109">Le funzionalità del linguaggio disabilitate da `-netcf` sono le stesse funzionalità del linguaggio non presenti nei file assegnati a `-sdkpath` .</span><span class="sxs-lookup"><span data-stu-id="7e21d-109">The language features disabled by `-netcf` are the same language features not present in the files targeted with `-sdkpath`.</span></span>

> [!NOTE]
> <span data-ttu-id="7e21d-110">L' `-netcf` opzione non è disponibile nell'ambiente di sviluppo di Visual Studio. è disponibile solo quando si esegue la compilazione dalla riga di comando.</span><span class="sxs-lookup"><span data-stu-id="7e21d-110">The `-netcf` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span> <span data-ttu-id="7e21d-111">L' `-netcf` opzione viene impostata quando viene caricato un progetto Visual Basic dispositivo.</span><span class="sxs-lookup"><span data-stu-id="7e21d-111">The `-netcf` option is set when a Visual Basic device project is loaded.</span></span>

<span data-ttu-id="7e21d-112">L' `-netcf` opzione modifica le funzionalità del linguaggio seguenti:</span><span class="sxs-lookup"><span data-stu-id="7e21d-112">The `-netcf` option changes the following language features:</span></span>

- <span data-ttu-id="7e21d-113">La parola chiave [ \<keyword> Statement end](../../language-reference/statements/end-keyword-statement.md) , che termina l'esecuzione di un programma, è disabilitata.</span><span class="sxs-lookup"><span data-stu-id="7e21d-113">The [End \<keyword> Statement](../../language-reference/statements/end-keyword-statement.md) keyword, which terminates execution of a program, is disabled.</span></span> <span data-ttu-id="7e21d-114">Il programma seguente compila ed esegue senza `-netcf` ma ha esito negativo in fase di compilazione con `-netcf` .</span><span class="sxs-lookup"><span data-stu-id="7e21d-114">The following program compiles and runs without `-netcf` but fails at compile time with `-netcf`.</span></span>

  [!code-vb[VbVbalrCompiler#34](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCompiler/VB/netcf.vb#34)]

- <span data-ttu-id="7e21d-115">L'associazione tardiva, in tutti i form, è disabilitata.</span><span class="sxs-lookup"><span data-stu-id="7e21d-115">Late binding, in all forms, is disabled.</span></span> <span data-ttu-id="7e21d-116">Gli errori in fase di compilazione vengono generati quando si rilevano scenari di associazione tardiva riconosciuti.</span><span class="sxs-lookup"><span data-stu-id="7e21d-116">Compile-time errors are generated when recognized late-binding scenarios are encountered.</span></span> <span data-ttu-id="7e21d-117">Il programma seguente compila ed esegue senza `-netcf` ma ha esito negativo in fase di compilazione con `-netcf` .</span><span class="sxs-lookup"><span data-stu-id="7e21d-117">The following program compiles and runs without `-netcf` but fails at compile time with `-netcf`.</span></span>

  [!code-vb[VbVbalrCompiler#35](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCompiler/VB/OptionStrictOff.vb#35)]

- <span data-ttu-id="7e21d-118">I modificatori [auto](../../language-reference/modifiers/auto.md), [ANSI](../../language-reference/modifiers/ansi.md)e [Unicode](../../language-reference/modifiers/unicode.md) sono disabilitati.</span><span class="sxs-lookup"><span data-stu-id="7e21d-118">The [Auto](../../language-reference/modifiers/auto.md), [Ansi](../../language-reference/modifiers/ansi.md), and [Unicode](../../language-reference/modifiers/unicode.md) modifiers are disabled.</span></span> <span data-ttu-id="7e21d-119">La sintassi dell' [istruzione Declare](../../language-reference/statements/declare-statement.md) viene inoltre modificata in `Declare Sub|Function name Lib "library" [Alias "alias"] [([arglist])]` .</span><span class="sxs-lookup"><span data-stu-id="7e21d-119">The syntax of the [Declare Statement](../../language-reference/statements/declare-statement.md) is also modified to `Declare Sub|Function name Lib "library" [Alias "alias"] [([arglist])]`.</span></span> <span data-ttu-id="7e21d-120">Nel codice seguente viene illustrato l'effetto di `-netcf` su una compilazione.</span><span class="sxs-lookup"><span data-stu-id="7e21d-120">The following code shows the effect of `-netcf` on a compilation.</span></span>

  [!code-vb[VbVbalrCompiler#36](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCompiler/VB/OptionStrictOff.vb#36)]

- <span data-ttu-id="7e21d-121">L'uso di Visual Basic parole chiave 6,0 che sono state rimosse da Visual Basic genera un errore diverso quando `-netcf` si usa.</span><span class="sxs-lookup"><span data-stu-id="7e21d-121">Using Visual Basic 6.0 keywords that were removed from Visual Basic generates a different error when `-netcf` is used.</span></span> <span data-ttu-id="7e21d-122">Ciò influiscono sui messaggi di errore per le parole chiave seguenti:</span><span class="sxs-lookup"><span data-stu-id="7e21d-122">This affects the error messages for the following keywords:</span></span>

  - `Open`

  - `Close`

  - `Put`

  - `Print`

  - `Write`

  - `Input`

  - `Lock`

  - `Unlock`

  - `Seek`

  - `Width`

  - `Name`

  - `FreeFile`

  - `EOF`

  - `Loc`

  - `LOF`

  - `Line`

## <a name="example"></a><span data-ttu-id="7e21d-123">Esempio</span><span class="sxs-lookup"><span data-stu-id="7e21d-123">Example</span></span>

<span data-ttu-id="7e21d-124">Il codice seguente viene compilato `Myfile.vb` con il .NET Compact Framework, usando le versioni di mscorlib. dll e Microsoft. VisualBasic. dll disponibili nella directory di installazione predefinita del .NET Compact Framework nell'unità C.</span><span class="sxs-lookup"><span data-stu-id="7e21d-124">The following code compiles `Myfile.vb` with the .NET Compact Framework, using the versions of mscorlib.dll and Microsoft.VisualBasic.dll found in the default installation directory of the .NET Compact Framework on the C drive.</span></span> <span data-ttu-id="7e21d-125">In genere, si utilizzerà la versione più recente del .NET Compact Framework.</span><span class="sxs-lookup"><span data-stu-id="7e21d-125">Typically, you would use the most recent version of the .NET Compact Framework.</span></span>

```console
vbc -netcf -sdkpath:"c:\Program Files\Microsoft Visual Studio .NET 2003\CompactFrameworkSDK\v1.0.5000\Windows CE " myfile.vb
```

## <a name="see-also"></a><span data-ttu-id="7e21d-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7e21d-126">See also</span></span>

- [<span data-ttu-id="7e21d-127">Compilatore della riga di comando di Visual Basic</span><span class="sxs-lookup"><span data-stu-id="7e21d-127">Visual Basic Command-Line Compiler</span></span>](index.md)
- [<span data-ttu-id="7e21d-128">Esempi di righe di comando di compilazione</span><span class="sxs-lookup"><span data-stu-id="7e21d-128">Sample Compilation Command Lines</span></span>](sample-compilation-command-lines.md)
- [<span data-ttu-id="7e21d-129">-sdkpath (</span><span class="sxs-lookup"><span data-stu-id="7e21d-129">-sdkpath</span></span>](sdkpath.md)
