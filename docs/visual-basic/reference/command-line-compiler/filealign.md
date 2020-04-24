---
title: -filealign
ms.date: 03/10/2018
helpviewer_keywords:
- sections compiler option [Visual Basic]
- alignment compiler option [Visual Basic]
- -filealign compiler option [Visual Basic]
- section alignment
- /filealign compiler option [Visual Basic]
- filealign compiler option [Visual Basic]
ms.assetid: cc61ec3d-ad38-4b28-9659-099d73cad099
ms.openlocfilehash: fef2652f591e713140c651a9cb0df1ea9e6236c8
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/07/2019
ms.locfileid: "72005594"
---
# <a name="-filealign"></a><span data-ttu-id="8b52a-102">-filealign</span><span class="sxs-lookup"><span data-stu-id="8b52a-102">-filealign</span></span>
<span data-ttu-id="8b52a-103">Specifica la posizione di allineamento per le sezioni del file di output.</span><span class="sxs-lookup"><span data-stu-id="8b52a-103">Specifies where to align the sections of the output file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8b52a-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8b52a-104">Syntax</span></span>  
  
```console  
-filealign:number  
```  
  
## <a name="arguments"></a><span data-ttu-id="8b52a-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="8b52a-105">Arguments</span></span>  
 `number`  
 <span data-ttu-id="8b52a-106">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="8b52a-106">Required.</span></span> <span data-ttu-id="8b52a-107">Valore che specifica l'allineamento delle sezioni nel file di output.</span><span class="sxs-lookup"><span data-stu-id="8b52a-107">A value that specifies the alignment of sections in the output file.</span></span> <span data-ttu-id="8b52a-108">I valori validi sono 512, 1024, 2048, 4096 e 8192.</span><span class="sxs-lookup"><span data-stu-id="8b52a-108">Valid values are 512, 1024, 2048, 4096, and 8192.</span></span> <span data-ttu-id="8b52a-109">I valori sono in byte.</span><span class="sxs-lookup"><span data-stu-id="8b52a-109">These values are in bytes.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8b52a-110">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="8b52a-110">Remarks</span></span>  
 <span data-ttu-id="8b52a-111">È possibile usare l' `-filealign` opzione per specificare l'allineamento delle sezioni nel file di output.</span><span class="sxs-lookup"><span data-stu-id="8b52a-111">You can use the `-filealign` option to specify the alignment of sections in your output file.</span></span> <span data-ttu-id="8b52a-112">Le sezioni sono blocchi di memoria contigua in un file eseguibile portabile (PE) che contiene il codice o i dati.</span><span class="sxs-lookup"><span data-stu-id="8b52a-112">Sections are blocks of contiguous memory in a Portable Executable (PE) file that contains either code or data.</span></span> <span data-ttu-id="8b52a-113">L' `-filealign` opzione consente di compilare l'applicazione con un allineamento non standard. per la maggior parte degli sviluppatori non è necessario usare questa opzione.</span><span class="sxs-lookup"><span data-stu-id="8b52a-113">The `-filealign` option lets you compile your application with a nonstandard alignment; most developers do not need to use this option.</span></span>  
  
 <span data-ttu-id="8b52a-114">Ogni sezione è allineata a un limite che corrisponde a un `-filealign` multiplo del valore.</span><span class="sxs-lookup"><span data-stu-id="8b52a-114">Each section is aligned on a boundary that is a multiple of the `-filealign` value.</span></span> <span data-ttu-id="8b52a-115">Non vi è alcun valore predefinito fisso.</span><span class="sxs-lookup"><span data-stu-id="8b52a-115">There is no fixed default.</span></span> <span data-ttu-id="8b52a-116">Se `-filealign` non viene specificato, il compilatore sceglie un valore predefinito in fase di compilazione.</span><span class="sxs-lookup"><span data-stu-id="8b52a-116">If `-filealign` is not specified, the compiler picks a default at compile time.</span></span>  
  
 <span data-ttu-id="8b52a-117">Specificando le dimensioni della sezione, è possibile modificare le dimensioni del file di output.</span><span class="sxs-lookup"><span data-stu-id="8b52a-117">By specifying the section size, you can change the size of the output file.</span></span> <span data-ttu-id="8b52a-118">La modifica delle dimensioni della sezione può essere utile per i programmi che verranno eseguiti su dispositivi di piccole dimensioni.</span><span class="sxs-lookup"><span data-stu-id="8b52a-118">Modifying section size may be useful for programs that will run on smaller devices.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="8b52a-119">L' `-filealign` opzione non è disponibile nell'ambiente di sviluppo di Visual Studio. è disponibile solo quando si esegue la compilazione dalla riga di comando.</span><span class="sxs-lookup"><span data-stu-id="8b52a-119">The `-filealign` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8b52a-120">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="8b52a-120">See also</span></span>

- [<span data-ttu-id="8b52a-121">Compilatore della riga di comando di Visual Basic</span><span class="sxs-lookup"><span data-stu-id="8b52a-121">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
