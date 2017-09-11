---
title: /filealign | Documenti di Microsoft
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- sections compiler option [Visual Basic]
- alignment compiler option [Visual Basic]
- -filealign compiler option [Visual Basic]
- section alignment
- /filealign compiler option [Visual Basic]
- filealign compiler option [Visual Basic]
ms.assetid: cc61ec3d-ad38-4b28-9659-099d73cad099
caps.latest.revision: 14
author: dotnet-bot
ms.author: dotnetcontent
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 5e0cd0a2a7e4c88df1087faee963f541c325b272
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017

---
# <a name="filealign"></a><span data-ttu-id="2228c-102">/filealign</span><span class="sxs-lookup"><span data-stu-id="2228c-102">/filealign</span></span>
<span data-ttu-id="2228c-103">Specifica la posizione di allineamento per le sezioni del file di output.</span><span class="sxs-lookup"><span data-stu-id="2228c-103">Specifies where to align the sections of the output file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2228c-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2228c-104">Syntax</span></span>  
  
```  
/filealign:number  
```  
  
## <a name="arguments"></a><span data-ttu-id="2228c-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="2228c-105">Arguments</span></span>  
 `number`  
 <span data-ttu-id="2228c-106">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="2228c-106">Required.</span></span> <span data-ttu-id="2228c-107">Un valore che specifica l'allineamento delle sezioni nel file di output.</span><span class="sxs-lookup"><span data-stu-id="2228c-107">A value that specifies the alignment of sections in the output file.</span></span> <span data-ttu-id="2228c-108">I valori validi sono 512, 1024, 2048, 4096 e 8192.</span><span class="sxs-lookup"><span data-stu-id="2228c-108">Valid values are 512, 1024, 2048, 4096, and 8192.</span></span> <span data-ttu-id="2228c-109">Questi valori sono espressi in byte.</span><span class="sxs-lookup"><span data-stu-id="2228c-109">These values are in bytes.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2228c-110">Note</span><span class="sxs-lookup"><span data-stu-id="2228c-110">Remarks</span></span>  
 <span data-ttu-id="2228c-111">È possibile utilizzare il `/filealign` opzione per specificare l'allineamento delle sezioni nel file di output.</span><span class="sxs-lookup"><span data-stu-id="2228c-111">You can use the `/filealign` option to specify the alignment of sections in your output file.</span></span> <span data-ttu-id="2228c-112">Le sezioni sono blocchi di memoria contigua in un file eseguibile portabile (PE) che contiene codice o dati.</span><span class="sxs-lookup"><span data-stu-id="2228c-112">Sections are blocks of contiguous memory in a Portable Executable (PE) file that contains either code or data.</span></span> <span data-ttu-id="2228c-113">Il `/filealign` opzione consente di compilare l'applicazione con un allineamento non standard, gli sviluppatori non è necessario utilizzare questa opzione.</span><span class="sxs-lookup"><span data-stu-id="2228c-113">The `/filealign` option lets you compile your application with a nonstandard alignment; most developers do not need to use this option.</span></span>  
  
 <span data-ttu-id="2228c-114">Ogni sezione è allineata a un limite che è un multiplo del `/filealign` valore.</span><span class="sxs-lookup"><span data-stu-id="2228c-114">Each section is aligned on a boundary that is a multiple of the `/filealign` value.</span></span> <span data-ttu-id="2228c-115">Non vi è alcun valore predefinito fisso.</span><span class="sxs-lookup"><span data-stu-id="2228c-115">There is no fixed default.</span></span> <span data-ttu-id="2228c-116">Se `/filealign` non è specificato, il compilatore sceglie un valore predefinito in fase di compilazione.</span><span class="sxs-lookup"><span data-stu-id="2228c-116">If `/filealign` is not specified, the compiler picks a default at compile time.</span></span>  
  
 <span data-ttu-id="2228c-117">Specificando le dimensioni della sezione, è possibile modificare le dimensioni del file di output.</span><span class="sxs-lookup"><span data-stu-id="2228c-117">By specifying the section size, you can change the size of the output file.</span></span> <span data-ttu-id="2228c-118">La modifica delle dimensioni di sezione può essere utile per i programmi che verranno eseguito su dispositivi di piccole dimensioni.</span><span class="sxs-lookup"><span data-stu-id="2228c-118">Modifying section size may be useful for programs that will run on smaller devices.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2228c-119">Il `/filealign` opzione non è disponibile all'interno dell'ambiente di sviluppo di Visual Studio, è disponibile solo durante la compilazione dalla riga di comando.</span><span class="sxs-lookup"><span data-stu-id="2228c-119">The `/filealign` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2228c-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2228c-120">See Also</span></span>  
 [<span data-ttu-id="2228c-121">Compilatore della riga di comando di Visual Basic</span><span class="sxs-lookup"><span data-stu-id="2228c-121">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
