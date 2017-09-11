---
title: /codepage (Visual Basic) | Documenti di Microsoft
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
- /codepage compiler option [Visual Basic]
- codepage compiler option [Visual Basic]
- -codepage compiler option [Visual Basic]
ms.assetid: be36ec33-6800-4505-838c-4124564f5cc9
caps.latest.revision: 17
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
ms.openlocfilehash: 6f4919bc4fc8eda700edbd80fead5b5d9fe0dba1
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017

---
# <a name="codepage-visual-basic"></a><span data-ttu-id="a5f38-102">/codepage (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a5f38-102">/codepage (Visual Basic)</span></span>
<span data-ttu-id="a5f38-103">Specifica la tabella codici da usare per tutti i file del codice sorgente nella compilazione.</span><span class="sxs-lookup"><span data-stu-id="a5f38-103">Specifies the code page to use for all source-code files in the compilation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a5f38-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a5f38-104">Syntax</span></span>  
  
```  
/codepage:id  
```  
  
## <a name="arguments"></a><span data-ttu-id="a5f38-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="a5f38-105">Arguments</span></span>  
  
|<span data-ttu-id="a5f38-106">Termine</span><span class="sxs-lookup"><span data-stu-id="a5f38-106">Term</span></span>|<span data-ttu-id="a5f38-107">Definizione</span><span class="sxs-lookup"><span data-stu-id="a5f38-107">Definition</span></span>|  
|---|---|  
|`id`|<span data-ttu-id="a5f38-108">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="a5f38-108">Required.</span></span> <span data-ttu-id="a5f38-109">Il compilatore utilizza la tabella codici specificata da `id` per interpretare la codifica dei file di origine.</span><span class="sxs-lookup"><span data-stu-id="a5f38-109">The compiler uses the code page specified by `id` to interpret the encoding of the source files.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a5f38-110">Note</span><span class="sxs-lookup"><span data-stu-id="a5f38-110">Remarks</span></span>  
 <span data-ttu-id="a5f38-111">Per compilare il codice sorgente salvato con una codifica specifica, è possibile utilizzare `/codepage` per specificare la tabella codici da utilizzare.</span><span class="sxs-lookup"><span data-stu-id="a5f38-111">To compile source code saved with a specific encoding, you can use `/codepage` to specify which code page should be used.</span></span> <span data-ttu-id="a5f38-112">Il `/codepage` opzione si applica a tutti i file di codice sorgente nella compilazione.</span><span class="sxs-lookup"><span data-stu-id="a5f38-112">The `/codepage` option applies to all source-code files in your compilation.</span></span> <span data-ttu-id="a5f38-113">Per ulteriori informazioni, vedere [codifica dei caratteri in .NET Framework](http://msdn.microsoft.com/library/bf6d9823-4c2d-48af-b280-919c5af66ae9).</span><span class="sxs-lookup"><span data-stu-id="a5f38-113">For more information, see [Character Encoding in the .NET Framework](http://msdn.microsoft.com/library/bf6d9823-4c2d-48af-b280-919c5af66ae9).</span></span>  
  
 <span data-ttu-id="a5f38-114">Il `/codepage` opzione non è necessaria se sono stati salvati i file di codice sorgente utilizzando la tabella codici ANSI corrente, Unicode o UTF-8 con una firma.</span><span class="sxs-lookup"><span data-stu-id="a5f38-114">The `/codepage` option is not needed if the source-code files were saved using the current ANSI code page, Unicode, or UTF-8 with a signature.</span></span> [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)]<span data-ttu-id="a5f38-115">Salva tutti i file di codice sorgente con la tabella codici ANSI corrente per impostazione predefinita, a meno che l'utente specifichi una codifica diversa nel **codifica** la finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="a5f38-115"> saves all source-code files with the current ANSI code page by default, unless the user specifies another encoding in the **Encoding** dialog box.</span></span> [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)]<span data-ttu-id="a5f38-116">Usa il **codifica** la finestra di dialogo per aprire il file di codice sorgente salvati con una tabella codici diversa.</span><span class="sxs-lookup"><span data-stu-id="a5f38-116"> uses the **Encoding** dialog box to open source-code files saved with a different code page.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a5f38-117">Il `/codepage` opzione non è disponibile all'interno di [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)] ambiente di sviluppo; è disponibile solo durante la compilazione dalla riga di comando.</span><span class="sxs-lookup"><span data-stu-id="a5f38-117">The `/codepage` option is not available from within the [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)] development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a5f38-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a5f38-118">See Also</span></span>  
 [<span data-ttu-id="a5f38-119">Compilatore della riga di comando di Visual Basic</span><span class="sxs-lookup"><span data-stu-id="a5f38-119">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
