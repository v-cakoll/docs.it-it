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
ms.openlocfilehash: db70749f28592ae6711b6d9544f8704af9416490
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2018
ms.locfileid: "50181722"
---
# <a name="-filealign"></a><span data-ttu-id="a3c8f-102">-filealign</span><span class="sxs-lookup"><span data-stu-id="a3c8f-102">-filealign</span></span>
<span data-ttu-id="a3c8f-103">Specifica la posizione di allineamento per le sezioni del file di output.</span><span class="sxs-lookup"><span data-stu-id="a3c8f-103">Specifies where to align the sections of the output file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a3c8f-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a3c8f-104">Syntax</span></span>  
  
```  
-filealign:number  
```  
  
## <a name="arguments"></a><span data-ttu-id="a3c8f-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="a3c8f-105">Arguments</span></span>  
 `number`  
 <span data-ttu-id="a3c8f-106">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="a3c8f-106">Required.</span></span> <span data-ttu-id="a3c8f-107">Un valore che specifica l'allineamento delle sezioni nel file di output.</span><span class="sxs-lookup"><span data-stu-id="a3c8f-107">A value that specifies the alignment of sections in the output file.</span></span> <span data-ttu-id="a3c8f-108">I valori validi sono 512, 1024, 2048, 4096 e 8192.</span><span class="sxs-lookup"><span data-stu-id="a3c8f-108">Valid values are 512, 1024, 2048, 4096, and 8192.</span></span> <span data-ttu-id="a3c8f-109">I valori sono in byte.</span><span class="sxs-lookup"><span data-stu-id="a3c8f-109">These values are in bytes.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a3c8f-110">Note</span><span class="sxs-lookup"><span data-stu-id="a3c8f-110">Remarks</span></span>  
 <span data-ttu-id="a3c8f-111">È possibile usare il `-filealign` opzione per specificare l'allineamento delle sezioni nel file di output.</span><span class="sxs-lookup"><span data-stu-id="a3c8f-111">You can use the `-filealign` option to specify the alignment of sections in your output file.</span></span> <span data-ttu-id="a3c8f-112">Le sezioni sono blocchi di memoria contigua in un file eseguibile portabile (PE) che contiene codice né dati.</span><span class="sxs-lookup"><span data-stu-id="a3c8f-112">Sections are blocks of contiguous memory in a Portable Executable (PE) file that contains either code or data.</span></span> <span data-ttu-id="a3c8f-113">Il `-filealign` opzione consente di compilare l'applicazione con un allineamento non standard, la maggior parte degli sviluppatori non sono necessario usare questa opzione.</span><span class="sxs-lookup"><span data-stu-id="a3c8f-113">The `-filealign` option lets you compile your application with a nonstandard alignment; most developers do not need to use this option.</span></span>  
  
 <span data-ttu-id="a3c8f-114">Ogni sezione è allineato in base a un limite è un multiplo di `-filealign` valore.</span><span class="sxs-lookup"><span data-stu-id="a3c8f-114">Each section is aligned on a boundary that is a multiple of the `-filealign` value.</span></span> <span data-ttu-id="a3c8f-115">Non vi è alcun valore predefinito fisso.</span><span class="sxs-lookup"><span data-stu-id="a3c8f-115">There is no fixed default.</span></span> <span data-ttu-id="a3c8f-116">Se `-filealign` non viene specificato, il compilatore sceglie un valore predefinito in fase di compilazione.</span><span class="sxs-lookup"><span data-stu-id="a3c8f-116">If `-filealign` is not specified, the compiler picks a default at compile time.</span></span>  
  
 <span data-ttu-id="a3c8f-117">Specifica le dimensioni della sezione, è possibile modificare le dimensioni del file di output.</span><span class="sxs-lookup"><span data-stu-id="a3c8f-117">By specifying the section size, you can change the size of the output file.</span></span> <span data-ttu-id="a3c8f-118">La modifica delle dimensioni della sezione può essere utile per i programmi che verranno eseguiti su dispositivi di piccole dimensioni.</span><span class="sxs-lookup"><span data-stu-id="a3c8f-118">Modifying section size may be useful for programs that will run on smaller devices.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a3c8f-119">Il `-filealign` opzione non è disponibile all'interno dell'ambiente di sviluppo di Visual Studio, è disponibile solo durante la compilazione dalla riga di comando.</span><span class="sxs-lookup"><span data-stu-id="a3c8f-119">The `-filealign` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a3c8f-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a3c8f-120">See Also</span></span>  
 [<span data-ttu-id="a3c8f-121">Compilatore della riga di comando di Visual Basic</span><span class="sxs-lookup"><span data-stu-id="a3c8f-121">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
