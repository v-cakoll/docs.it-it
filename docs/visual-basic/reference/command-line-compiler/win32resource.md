---
title: /win32resource | Documenti di Microsoft
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- /win32resource
- win32resource
dev_langs:
- VB
helpviewer_keywords:
- /win32resource compiler option [Visual Basic]
- -win32resource compiler option [Visual Basic]
- win32resource compiler option [Visual Basic]
ms.assetid: e226946d-19ce-4cc9-91f5-aed24f77aa2b
caps.latest.revision: 13
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
ms.openlocfilehash: dc6bbb5948a5dd505f0fc4d1c8a86650214d657a
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017

---
# <a name="win32resource"></a><span data-ttu-id="d6a18-102">/win32resource</span><span class="sxs-lookup"><span data-stu-id="d6a18-102">/win32resource</span></span>
<span data-ttu-id="d6a18-103">Inserisce un file di risorse Win32 nel file di output.</span><span class="sxs-lookup"><span data-stu-id="d6a18-103">Inserts a Win32 resource file in the output file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d6a18-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d6a18-104">Syntax</span></span>  
  
```  
/win32resource:filename  
```  
  
## <a name="arguments"></a><span data-ttu-id="d6a18-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="d6a18-105">Arguments</span></span>  
 `filename`  
 <span data-ttu-id="d6a18-106">Il nome del file di risorse da aggiungere al file di output.</span><span class="sxs-lookup"><span data-stu-id="d6a18-106">The name of the resource file to add to your output file.</span></span> <span data-ttu-id="d6a18-107">Racchiudere il nome del file tra virgolette ("") se contiene uno spazio.</span><span class="sxs-lookup"><span data-stu-id="d6a18-107">Enclose the file name in quotation marks (" ") if it contains a space.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d6a18-108">Note</span><span class="sxs-lookup"><span data-stu-id="d6a18-108">Remarks</span></span>  
 <span data-ttu-id="d6a18-109">È possibile creare un file di risorse Win32 con il compilatore di risorse (RC) di Microsoft Windows.</span><span class="sxs-lookup"><span data-stu-id="d6a18-109">You can create a Win32 resource file with the Microsoft Windows Resource Compiler (RC).</span></span>  
  
 <span data-ttu-id="d6a18-110">Una risorsa Win32 può contenere versione o informazioni bitmap (icona) che consente di identificare l'applicazione in **Esplora File**.</span><span class="sxs-lookup"><span data-stu-id="d6a18-110">A Win32 resource can contain version or bitmap (icon) information that helps identify your application in **File Explorer**.</span></span> <span data-ttu-id="d6a18-111">Se non si specifica `/win32resource`, il compilatore genera informazioni di versione basate sulla versione dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="d6a18-111">If you do not specify `/win32resource`, the compiler generates version information based on the assembly version.</span></span> <span data-ttu-id="d6a18-112">Il `/win32resource` e `/win32icon` opzioni si escludono a vicenda.</span><span class="sxs-lookup"><span data-stu-id="d6a18-112">The `/win32resource` and `/win32icon` options are mutually exclusive.</span></span>  
  
 <span data-ttu-id="d6a18-113">Vedere [/linkresource (Visual Basic)](../../../visual-basic/reference/command-line-compiler/linkresource.md) per fare riferimento a un [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] file di risorse, o [/resource (Visual Basic)](../../../visual-basic/reference/command-line-compiler/resource.md) per collegare un [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] file di risorse.</span><span class="sxs-lookup"><span data-stu-id="d6a18-113">See [/linkresource (Visual Basic)](../../../visual-basic/reference/command-line-compiler/linkresource.md) to reference a [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] resource file, or [/resource (Visual Basic)](../../../visual-basic/reference/command-line-compiler/resource.md) to attach a [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] resource file.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d6a18-114">Il `/win32resource` opzione non è disponibile all'interno dell'ambiente di sviluppo di Visual Studio, è disponibile solo durante la compilazione dalla riga di comando.</span><span class="sxs-lookup"><span data-stu-id="d6a18-114">The `/win32resource` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d6a18-115">Esempio</span><span class="sxs-lookup"><span data-stu-id="d6a18-115">Example</span></span>  
 <span data-ttu-id="d6a18-116">Il codice seguente Compila `In.vb` e allegare un file di risorse Win32 `Rf.res`:</span><span class="sxs-lookup"><span data-stu-id="d6a18-116">The following code compiles `In.vb` and attaches a Win32 resource file, `Rf.res`:</span></span>  
  
```  
vbc /win32resource:rf.res in.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="d6a18-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d6a18-117">See Also</span></span>  
 <span data-ttu-id="d6a18-118">[Compilatore della riga di comando di Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md) </span><span class="sxs-lookup"><span data-stu-id="d6a18-118">[Visual Basic Command-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md) </span></span>  
<span data-ttu-id="d6a18-119"> [Esempi di righe di comando di compilazione](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)</span><span class="sxs-lookup"><span data-stu-id="d6a18-119"> [Sample Compilation Command Lines](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)</span></span>
