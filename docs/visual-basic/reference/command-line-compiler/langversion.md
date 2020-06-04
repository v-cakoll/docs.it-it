---
title: -langversion
ms.date: 03/10/2018
helpviewer_keywords:
- /langversion compiler option [Visual Basic]
- langversion compiler option [Visual Basic]
- -langversion compiler option [Visual Basic]
ms.assetid: 59b7b0c8-2dde-4e9b-94e7-0237f7e0bafb
ms.openlocfilehash: 271606ac021e6afcb28fdac3e1bc86e1aaba7d2b
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84408538"
---
# <a name="-langversion-visual-basic"></a><span data-ttu-id="f55a0-102">-langversion (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f55a0-102">-langversion (Visual Basic)</span></span>
<span data-ttu-id="f55a0-103">Fa in modo che il compilatore accetti solo la sintassi inclusa nella versione della lingua Visual Basic specificata.</span><span class="sxs-lookup"><span data-stu-id="f55a0-103">Causes the compiler to accept only syntax that is included in the specified Visual Basic language version.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f55a0-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f55a0-104">Syntax</span></span>  
  
```console  
-langversion:version  
```  
  
## <a name="arguments"></a><span data-ttu-id="f55a0-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="f55a0-105">Arguments</span></span>  
 `version`  
 <span data-ttu-id="f55a0-106">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="f55a0-106">Required.</span></span> <span data-ttu-id="f55a0-107">La versione del linguaggio da utilizzare durante la compilazione.</span><span class="sxs-lookup"><span data-stu-id="f55a0-107">The language version to be used during the compilation.</span></span> <span data-ttu-id="f55a0-108">I valori accettati sono `9` ,, `10` `11` , `12` , `14` , `15` , `15.3` , `15.5` `default` e `latest` .</span><span class="sxs-lookup"><span data-stu-id="f55a0-108">Accepted values are `9`, `10`, `11`, `12`, `14`, `15`, `15.3`, `15.5`, `default` and `latest`.</span></span>

 <span data-ttu-id="f55a0-109">I numeri interi possono essere specificati anche usando `.0` come versione secondaria, ad esempio `11.0` .</span><span class="sxs-lookup"><span data-stu-id="f55a0-109">Any of the whole numbers may also be specified using `.0` as the minor version, for example, `11.0`.</span></span>

 <span data-ttu-id="f55a0-110">È possibile visualizzare l'elenco di tutti i valori possibili specificando `-langversion:?` nella riga di comando.</span><span class="sxs-lookup"><span data-stu-id="f55a0-110">You can see the list of all possible values by specifying `-langversion:?` on the command line.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f55a0-111">Commenti</span><span class="sxs-lookup"><span data-stu-id="f55a0-111">Remarks</span></span>  
 <span data-ttu-id="f55a0-112">L' `-langversion` opzione specifica la sintassi accettata dal compilatore.</span><span class="sxs-lookup"><span data-stu-id="f55a0-112">The `-langversion` option specifies what syntax the compiler accepts.</span></span> <span data-ttu-id="f55a0-113">Se, ad esempio, si specifica che la versione del linguaggio è 9,0, il compilatore genera errori per la sintassi valida solo nella versione 10,0 e successive.</span><span class="sxs-lookup"><span data-stu-id="f55a0-113">For example, if you specify that the language version is 9.0, the compiler generates errors for syntax that is valid only in version 10.0 and later.</span></span>  
  
 <span data-ttu-id="f55a0-114">È possibile utilizzare questa opzione quando si sviluppano applicazioni destinate a versioni diverse del .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="f55a0-114">You can use this option when you develop applications that target different versions of the .NET Framework.</span></span> <span data-ttu-id="f55a0-115">Ad esempio, se la destinazione è .NET Framework 3,5, è possibile usare questa opzione per assicurarsi di non usare la sintassi della versione 10,0 del linguaggio.</span><span class="sxs-lookup"><span data-stu-id="f55a0-115">For example, if you are targeting .NET Framework 3.5, you could use this option to ensure that you do not use syntax from language version 10.0.</span></span>  
  
 <span data-ttu-id="f55a0-116">È possibile impostare `-langversion` direttamente solo tramite la riga di comando.</span><span class="sxs-lookup"><span data-stu-id="f55a0-116">You can set `-langversion` directly only by using the command line.</span></span> <span data-ttu-id="f55a0-117">Per ulteriori informazioni, vedere la pagina relativa alla [destinazione di una specifica .NET Framework versione](/visualstudio/ide/visual-studio-multi-targeting-overview).</span><span class="sxs-lookup"><span data-stu-id="f55a0-117">For more information, see [Targeting a Specific .NET Framework Version](/visualstudio/ide/visual-studio-multi-targeting-overview).</span></span>  
  
## <a name="example"></a><span data-ttu-id="f55a0-118">Esempio</span><span class="sxs-lookup"><span data-stu-id="f55a0-118">Example</span></span>  
 <span data-ttu-id="f55a0-119">Il codice seguente viene compilato `sample.vb` per Visual Basic 9,0.</span><span class="sxs-lookup"><span data-stu-id="f55a0-119">The following code compiles `sample.vb` for Visual Basic 9.0.</span></span>  
  
```console  
vbc -langversion:9.0 sample.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="f55a0-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f55a0-120">See also</span></span>

- [<span data-ttu-id="f55a0-121">Compilatore della riga di comando di Visual Basic</span><span class="sxs-lookup"><span data-stu-id="f55a0-121">Visual Basic Command-Line Compiler</span></span>](index.md)
- [<span data-ttu-id="f55a0-122">Esempi di righe di comando di compilazione</span><span class="sxs-lookup"><span data-stu-id="f55a0-122">Sample Compilation Command Lines</span></span>](sample-compilation-command-lines.md)
- [<span data-ttu-id="f55a0-123">Sviluppo per una versione specifica di .NET Framework</span><span class="sxs-lookup"><span data-stu-id="f55a0-123">Targeting a Specific .NET Framework Version</span></span>](/visualstudio/ide/visual-studio-multi-targeting-overview)
