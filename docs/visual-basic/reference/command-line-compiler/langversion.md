---
title: -langversion (Visual Basic)
ms.date: 03/10/2018
helpviewer_keywords:
- /langversion compiler option [Visual Basic]
- langversion compiler option [Visual Basic]
- -langversion compiler option [Visual Basic]
ms.assetid: 59b7b0c8-2dde-4e9b-94e7-0237f7e0bafb
ms.openlocfilehash: 6fffe264377474bba14f6f086b521ccf9bd04adf
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54534459"
---
# <a name="-langversion-visual-basic"></a><span data-ttu-id="b74f7-102">-langversion (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b74f7-102">-langversion (Visual Basic)</span></span>
<span data-ttu-id="b74f7-103">Indica al compilatore di accettare solo sintassi inclusa nella versione specificata del linguaggio Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="b74f7-103">Causes the compiler to accept only syntax that is included in the specified Visual Basic language version.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b74f7-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b74f7-104">Syntax</span></span>  
  
```  
-langversion:version  
```  
  
## <a name="arguments"></a><span data-ttu-id="b74f7-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="b74f7-105">Arguments</span></span>  
 `version`  
 <span data-ttu-id="b74f7-106">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="b74f7-106">Required.</span></span> <span data-ttu-id="b74f7-107">Versione del linguaggio da utilizzare durante la compilazione.</span><span class="sxs-lookup"><span data-stu-id="b74f7-107">The language version to be used during the compilation.</span></span> <span data-ttu-id="b74f7-108">Valori accettati sono `9`, `10`, `11`, `12`, `14`, `15`, `15.3`, `15.5`, `default` e `latest`.</span><span class="sxs-lookup"><span data-stu-id="b74f7-108">Accepted values are `9`, `10`, `11`, `12`, `14`, `15`, `15.3`, `15.5`, `default` and `latest`.</span></span>

 <span data-ttu-id="b74f7-109">Uno dei numeri interi può anche essere specificato tramite `.0` come la versione secondaria, ad esempio, `11.0`.</span><span class="sxs-lookup"><span data-stu-id="b74f7-109">Any of the whole numbers may also be specified using `.0` as the minor version, for example, `11.0`.</span></span>

 <span data-ttu-id="b74f7-110">È possibile visualizzare l'elenco di tutti i possibili valori specificando `-langversion:?` nella riga di comando.</span><span class="sxs-lookup"><span data-stu-id="b74f7-110">You can see the list of all possible values by specifying `-langversion:?` on the command line.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b74f7-111">Note</span><span class="sxs-lookup"><span data-stu-id="b74f7-111">Remarks</span></span>  
 <span data-ttu-id="b74f7-112">Il `-langversion` opzione specifica quale sintassi il compilatore accetta.</span><span class="sxs-lookup"><span data-stu-id="b74f7-112">The `-langversion` option specifies what syntax the compiler accepts.</span></span> <span data-ttu-id="b74f7-113">Ad esempio, se si specifica che la versione del linguaggio è 9.0, il compilatore genera errori di sintassi che è valida solo nella versione 10.0 e versioni successive.</span><span class="sxs-lookup"><span data-stu-id="b74f7-113">For example, if you specify that the language version is 9.0, the compiler generates errors for syntax that is valid only in version 10.0 and later.</span></span>  
  
 <span data-ttu-id="b74f7-114">È possibile usare questa opzione quando si sviluppano applicazioni destinati a versioni diverse di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="b74f7-114">You can use this option when you develop applications that target different versions of the .NET Framework.</span></span> <span data-ttu-id="b74f7-115">Ad esempio, se si usa .NET Framework 3.5, è possibile utilizzare questa opzione per assicurarsi di non usare la sintassi di linguaggio versione 10.0.</span><span class="sxs-lookup"><span data-stu-id="b74f7-115">For example, if you are targeting .NET Framework 3.5, you could use this option to ensure that you do not use syntax from language version 10.0.</span></span>  
  
 <span data-ttu-id="b74f7-116">È possibile impostare `-langversion` direttamente solo tramite la riga di comando.</span><span class="sxs-lookup"><span data-stu-id="b74f7-116">You can set `-langversion` directly only by using the command line.</span></span> <span data-ttu-id="b74f7-117">Per altre informazioni, vedere [Sviluppo per una versione specifica di .NET Framework](/visualstudio/ide/targeting-a-specific-dotnet-framework-version).</span><span class="sxs-lookup"><span data-stu-id="b74f7-117">For more information, see [Targeting a Specific .NET Framework Version](/visualstudio/ide/targeting-a-specific-dotnet-framework-version).</span></span>  
  
## <a name="example"></a><span data-ttu-id="b74f7-118">Esempio</span><span class="sxs-lookup"><span data-stu-id="b74f7-118">Example</span></span>  
 <span data-ttu-id="b74f7-119">Il codice seguente Compila `sample.vb` per Visual Basic 9.0.</span><span class="sxs-lookup"><span data-stu-id="b74f7-119">The following code compiles `sample.vb` for Visual Basic 9.0.</span></span>  
  
```console  
vbc -langversion:9.0 sample.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="b74f7-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b74f7-120">See also</span></span>
- [<span data-ttu-id="b74f7-121">Compilatore della riga di comando di Visual Basic</span><span class="sxs-lookup"><span data-stu-id="b74f7-121">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="b74f7-122">Esempi di righe di comando di compilazione</span><span class="sxs-lookup"><span data-stu-id="b74f7-122">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [<span data-ttu-id="b74f7-123">Sviluppo per una versione specifica di .NET Framework</span><span class="sxs-lookup"><span data-stu-id="b74f7-123">Targeting a Specific .NET Framework Version</span></span>](/visualstudio/ide/targeting-a-specific-dotnet-framework-version)
