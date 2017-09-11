---
title: /langversion (Visual Basic) | Documenti di Microsoft
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
- /langversion compiler option [Visual Basic]
- langversion compiler option [Visual Basic]
- -langversion compiler option [Visual Basic]
ms.assetid: 59b7b0c8-2dde-4e9b-94e7-0237f7e0bafb
caps.latest.revision: 8
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
ms.openlocfilehash: 56411df907bd5ff0416e6d0539cbe46df3b34947
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017

---
# <a name="langversion-visual-basic"></a><span data-ttu-id="b8f1a-102">/langversion (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b8f1a-102">/langversion (Visual Basic)</span></span>
<span data-ttu-id="b8f1a-103">Indica al compilatore di accettare solo la sintassi che è incluso nella versione specificata del linguaggio Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="b8f1a-103">Causes the compiler to accept only syntax that is included in the specified Visual Basic language version.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b8f1a-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b8f1a-104">Syntax</span></span>  
  
```  
/langversion:version  
```  
  
## <a name="arguments"></a><span data-ttu-id="b8f1a-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="b8f1a-105">Arguments</span></span>  
 `version`  
 <span data-ttu-id="b8f1a-106">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="b8f1a-106">Required.</span></span> <span data-ttu-id="b8f1a-107">La versione della lingua da utilizzare durante la compilazione.</span><span class="sxs-lookup"><span data-stu-id="b8f1a-107">The language version to be used during the compilation.</span></span> <span data-ttu-id="b8f1a-108">Valori accettati sono `9`, `9.0`, `10`, e `10.0`.</span><span class="sxs-lookup"><span data-stu-id="b8f1a-108">Accepted values are `9`, `9.0`, `10`, and `10.0`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b8f1a-109">Note</span><span class="sxs-lookup"><span data-stu-id="b8f1a-109">Remarks</span></span>  
 <span data-ttu-id="b8f1a-110">Il `/langversion` opzione specifica quale il compilatore accetta una sintassi.</span><span class="sxs-lookup"><span data-stu-id="b8f1a-110">The `/langversion` option specifies what syntax the compiler accepts.</span></span> <span data-ttu-id="b8f1a-111">Ad esempio, se si specifica che la versione in lingua è 9.0, il compilatore genera errori di sintassi che è valida solo nella versione 10.0 e versioni successive.</span><span class="sxs-lookup"><span data-stu-id="b8f1a-111">For example, if you specify that the language version is 9.0, the compiler generates errors for syntax that is valid only in version 10.0 and later.</span></span>  
  
 <span data-ttu-id="b8f1a-112">È possibile utilizzare questa opzione quando si sviluppano applicazioni che diverse versioni di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="b8f1a-112">You can use this option when you develop applications that target different versions of the .NET Framework.</span></span> <span data-ttu-id="b8f1a-113">Ad esempio, se la destinazione è .NET Framework 3.5, è possibile utilizzare questa opzione per garantire che non si utilizza la sintassi di linguaggio versione 10.0.</span><span class="sxs-lookup"><span data-stu-id="b8f1a-113">For example, if you are targeting .NET Framework 3.5, you could use this option to ensure that you do not use syntax from language version 10.0.</span></span>  
  
 <span data-ttu-id="b8f1a-114">È possibile impostare `/langversion` direttamente solo utilizzando la riga di comando.</span><span class="sxs-lookup"><span data-stu-id="b8f1a-114">You can set `/langversion` directly only by using the command line.</span></span> <span data-ttu-id="b8f1a-115">Per altre informazioni, vedere [Sviluppo per una versione specifica di .NET Framework](https://docs.microsoft.com/visualstudio/ide/targeting-a-specific-dotnet-framework-version).</span><span class="sxs-lookup"><span data-stu-id="b8f1a-115">For more information, see [Targeting a Specific .NET Framework Version](https://docs.microsoft.com/visualstudio/ide/targeting-a-specific-dotnet-framework-version).</span></span>  
  
## <a name="example"></a><span data-ttu-id="b8f1a-116">Esempio</span><span class="sxs-lookup"><span data-stu-id="b8f1a-116">Example</span></span>  
 <span data-ttu-id="b8f1a-117">Il codice seguente Compila `sample.vb` per Visual Basic 9.0.</span><span class="sxs-lookup"><span data-stu-id="b8f1a-117">The following code compiles `sample.vb` for Visual Basic 9.0.</span></span>  
  
```  
vbc /langversion:9.0 sample.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="b8f1a-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b8f1a-118">See Also</span></span>  
 <span data-ttu-id="b8f1a-119">[Compilatore della riga di comando di Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md) </span><span class="sxs-lookup"><span data-stu-id="b8f1a-119">[Visual Basic Command-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md) </span></span>  
<span data-ttu-id="b8f1a-120"> [Esempi di righe di comando compilazione](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md) </span><span class="sxs-lookup"><span data-stu-id="b8f1a-120"> [Sample Compilation Command Lines](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md) </span></span>  
<span data-ttu-id="b8f1a-121"> [Sviluppo per una versione specifica di .NET Framework](https://docs.microsoft.com/visualstudio/ide/targeting-a-specific-dotnet-framework-version)</span><span class="sxs-lookup"><span data-stu-id="b8f1a-121"> [Targeting a Specific .NET Framework Version](https://docs.microsoft.com/visualstudio/ide/targeting-a-specific-dotnet-framework-version)</span></span>
