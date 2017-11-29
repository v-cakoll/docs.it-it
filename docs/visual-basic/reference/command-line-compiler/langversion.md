---
title: /langversion (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- /langversion compiler option [Visual Basic]
- langversion compiler option [Visual Basic]
- -langversion compiler option [Visual Basic]
ms.assetid: 59b7b0c8-2dde-4e9b-94e7-0237f7e0bafb
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: cfe91588471cc8410b25addea8d66a0388c9c5be
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="langversion-visual-basic"></a><span data-ttu-id="2b6b9-102">/langversion (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2b6b9-102">/langversion (Visual Basic)</span></span>
<span data-ttu-id="2b6b9-103">Indica al compilatore di accettare solo la sintassi che è incluso nella versione specificata del linguaggio Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="2b6b9-103">Causes the compiler to accept only syntax that is included in the specified Visual Basic language version.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2b6b9-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2b6b9-104">Syntax</span></span>  
  
```  
/langversion:version  
```  
  
## <a name="arguments"></a><span data-ttu-id="2b6b9-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="2b6b9-105">Arguments</span></span>  
 `version`  
 <span data-ttu-id="2b6b9-106">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="2b6b9-106">Required.</span></span> <span data-ttu-id="2b6b9-107">La versione della lingua da utilizzare durante la compilazione.</span><span class="sxs-lookup"><span data-stu-id="2b6b9-107">The language version to be used during the compilation.</span></span> <span data-ttu-id="2b6b9-108">I valori accettati sono `9`, `9.0`, `10`, e `10.0`.</span><span class="sxs-lookup"><span data-stu-id="2b6b9-108">Accepted values are `9`, `9.0`, `10`, and `10.0`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2b6b9-109">Note</span><span class="sxs-lookup"><span data-stu-id="2b6b9-109">Remarks</span></span>  
 <span data-ttu-id="2b6b9-110">Il `/langversion` opzione specifica quale il compilatore accetta di sintassi.</span><span class="sxs-lookup"><span data-stu-id="2b6b9-110">The `/langversion` option specifies what syntax the compiler accepts.</span></span> <span data-ttu-id="2b6b9-111">Ad esempio, se si specifica che la lingua è 9.0, il compilatore genera errori di sintassi che è valida solo nella versione 10.0 e versioni successive.</span><span class="sxs-lookup"><span data-stu-id="2b6b9-111">For example, if you specify that the language version is 9.0, the compiler generates errors for syntax that is valid only in version 10.0 and later.</span></span>  
  
 <span data-ttu-id="2b6b9-112">È possibile utilizzare questa opzione quando si sviluppano applicazioni che diverse versioni di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="2b6b9-112">You can use this option when you develop applications that target different versions of the .NET Framework.</span></span> <span data-ttu-id="2b6b9-113">Ad esempio, se la destinazione è .NET Framework 3.5, è possibile utilizzare questa opzione per assicurarsi che non utilizzino la sintassi di linguaggio versione 10.0.</span><span class="sxs-lookup"><span data-stu-id="2b6b9-113">For example, if you are targeting .NET Framework 3.5, you could use this option to ensure that you do not use syntax from language version 10.0.</span></span>  
  
 <span data-ttu-id="2b6b9-114">È possibile impostare `/langversion` direttamente solo tramite la riga di comando.</span><span class="sxs-lookup"><span data-stu-id="2b6b9-114">You can set `/langversion` directly only by using the command line.</span></span> <span data-ttu-id="2b6b9-115">Per altre informazioni, vedere [Sviluppo per una versione specifica di .NET Framework](/visualstudio/ide/targeting-a-specific-dotnet-framework-version).</span><span class="sxs-lookup"><span data-stu-id="2b6b9-115">For more information, see [Targeting a Specific .NET Framework Version](/visualstudio/ide/targeting-a-specific-dotnet-framework-version).</span></span>  
  
## <a name="example"></a><span data-ttu-id="2b6b9-116">Esempio</span><span class="sxs-lookup"><span data-stu-id="2b6b9-116">Example</span></span>  
 <span data-ttu-id="2b6b9-117">Il codice seguente Compila `sample.vb` per Visual Basic 9.0.</span><span class="sxs-lookup"><span data-stu-id="2b6b9-117">The following code compiles `sample.vb` for Visual Basic 9.0.</span></span>  
  
```  
vbc /langversion:9.0 sample.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="2b6b9-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2b6b9-118">See Also</span></span>  
 [<span data-ttu-id="2b6b9-119">Compilatore della riga di comando di Visual Basic</span><span class="sxs-lookup"><span data-stu-id="2b6b9-119">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="2b6b9-120">Esempi di righe di comando di compilazione</span><span class="sxs-lookup"><span data-stu-id="2b6b9-120">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)  
 [<span data-ttu-id="2b6b9-121">Sviluppo per una versione specifica di .NET Framework</span><span class="sxs-lookup"><span data-stu-id="2b6b9-121">Targeting a Specific .NET Framework Version</span></span>](/visualstudio/ide/targeting-a-specific-dotnet-framework-version)
