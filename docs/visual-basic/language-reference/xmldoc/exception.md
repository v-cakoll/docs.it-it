---
title: '&lt;eccezione&gt; (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- <exception> XML tag
- exception XML tag
ms.assetid: c0517549-171e-4dae-ab88-a9c1700b6eee
ms.openlocfilehash: 047805ad91d87550da80448fd10883ae58647bd6
ms.sourcegitcommit: 67de6cb5dd66a19f2180ba7e4d7aecc697f8a963
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/10/2018
ms.locfileid: "44337694"
---
# <a name="ltexceptiongt-visual-basic"></a><span data-ttu-id="70410-102">&lt;eccezione&gt; (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="70410-102">&lt;exception&gt; (Visual Basic)</span></span>
<span data-ttu-id="70410-103">Specifica le eccezioni che possono essere generate.</span><span class="sxs-lookup"><span data-stu-id="70410-103">Specifies which exceptions can be thrown.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="70410-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="70410-104">Syntax</span></span>  
  
```xml  
<exception cref="member">description</exception>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="70410-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="70410-105">Parameters</span></span>  
 `member`  
 <span data-ttu-id="70410-106">Riferimento ad un'eccezione disponibile dall'ambiente di compilazione corrente.</span><span class="sxs-lookup"><span data-stu-id="70410-106">A reference to an exception that is available from the current compilation environment.</span></span> <span data-ttu-id="70410-107">Il compilatore controlla che l'eccezione specificata esista e converte `member` nel nome canonico dell'elemento nel file XML di output.</span><span class="sxs-lookup"><span data-stu-id="70410-107">The compiler checks that the given exception exists and translates `member` to the canonical element name in the output XML.</span></span> <span data-ttu-id="70410-108">`member` deve essere racchiuso tra virgolette doppie (" ").</span><span class="sxs-lookup"><span data-stu-id="70410-108">`member` must appear within double quotation marks (" ").</span></span>  
  
 `description`  
 <span data-ttu-id="70410-109">Descrizione.</span><span class="sxs-lookup"><span data-stu-id="70410-109">A description.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="70410-110">Note</span><span class="sxs-lookup"><span data-stu-id="70410-110">Remarks</span></span>  
 <span data-ttu-id="70410-111">Usare il `<exception>` tag per specificare le eccezioni che possono essere generate.</span><span class="sxs-lookup"><span data-stu-id="70410-111">Use the `<exception>` tag to specify which exceptions can be thrown.</span></span> <span data-ttu-id="70410-112">Questo tag viene applicato a una definizione di metodo.</span><span class="sxs-lookup"><span data-stu-id="70410-112">This tag is applied to a method definition.</span></span>  
  
 <span data-ttu-id="70410-113">Compilare con [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) per elaborare i commenti relativi alla documentazione in un file.</span><span class="sxs-lookup"><span data-stu-id="70410-113">Compile with [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="70410-114">Esempio</span><span class="sxs-lookup"><span data-stu-id="70410-114">Example</span></span>  
 <span data-ttu-id="70410-115">Questo esempio Usa la `<exception>` tag per descrivere un'eccezione che il `IntDivide` funzione può generare.</span><span class="sxs-lookup"><span data-stu-id="70410-115">This example uses the `<exception>` tag to describe an exception that the `IntDivide` function can throw.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#3](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/exception_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="70410-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="70410-116">See Also</span></span>  
 [<span data-ttu-id="70410-117">Tag di commento XML</span><span class="sxs-lookup"><span data-stu-id="70410-117">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
