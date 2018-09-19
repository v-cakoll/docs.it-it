---
title: '&lt;autorizzazione&gt; (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- <permission> XML tag
- permission XML tag
ms.assetid: 0edf0500-5cd7-49c0-9255-64c48f972b77
ms.openlocfilehash: bcec5d968f5d0c5400c28e772df151b164888a47
ms.sourcegitcommit: 3ab9254890a52a50762995fa6d7d77a00348db7e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/19/2018
ms.locfileid: "46323298"
---
# <a name="ltpermissiongt-visual-basic"></a><span data-ttu-id="9a253-102">&lt;autorizzazione&gt; (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9a253-102">&lt;permission&gt; (Visual Basic)</span></span>
<span data-ttu-id="9a253-103">Specifica un'autorizzazione necessaria per il membro.</span><span class="sxs-lookup"><span data-stu-id="9a253-103">Specifies a required permission for the member.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9a253-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9a253-104">Syntax</span></span>  
  
```xml  
<permission cref="member">description</permission>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9a253-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="9a253-105">Parameters</span></span>  
 `member`  
 <span data-ttu-id="9a253-106">Riferimento a un membro o a un campo disponibile per essere chiamato dall'ambiente di compilazione corrente.</span><span class="sxs-lookup"><span data-stu-id="9a253-106">A reference to a member or field that is available to be called from the current compilation environment.</span></span> <span data-ttu-id="9a253-107">Il compilatore verifica l'esistenza dell'elemento di codice specificato e converte `member` nel nome canonico dell'elemento nel file XML di output.</span><span class="sxs-lookup"><span data-stu-id="9a253-107">The compiler checks that the given code element exists and translates `member` to the canonical element name in the output XML.</span></span> <span data-ttu-id="9a253-108">Racchiudere `member` racchiuso tra virgolette ("").</span><span class="sxs-lookup"><span data-stu-id="9a253-108">Enclose `member` in quotation marks (" ").</span></span>  
  
 `description`  
 <span data-ttu-id="9a253-109">Descrizione dell'accesso al membro.</span><span class="sxs-lookup"><span data-stu-id="9a253-109">A description of the access to the member.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9a253-110">Note</span><span class="sxs-lookup"><span data-stu-id="9a253-110">Remarks</span></span>  
 <span data-ttu-id="9a253-111">Usare il `<permission>` tag per documentare l'accesso di un membro.</span><span class="sxs-lookup"><span data-stu-id="9a253-111">Use the `<permission>` tag to document the access of a member.</span></span> <span data-ttu-id="9a253-112">Usare il <xref:System.Security.PermissionSet> classe per specificare l'accesso a un membro.</span><span class="sxs-lookup"><span data-stu-id="9a253-112">Use the <xref:System.Security.PermissionSet> class to specify access to a member.</span></span>  
  
 <span data-ttu-id="9a253-113">Compilare con [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) per elaborare i commenti relativi alla documentazione in un file.</span><span class="sxs-lookup"><span data-stu-id="9a253-113">Compile with [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9a253-114">Esempio</span><span class="sxs-lookup"><span data-stu-id="9a253-114">Example</span></span>  
 <span data-ttu-id="9a253-115">Questo esempio Usa la `<permission>` tag per descrivere che il <xref:System.Security.Permissions.FileIOPermission> richiesto dal `ReadFile` (metodo).</span><span class="sxs-lookup"><span data-stu-id="9a253-115">This example uses the `<permission>` tag to describe that the <xref:System.Security.Permissions.FileIOPermission> is required by the `ReadFile` method.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#7](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/permission_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="9a253-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9a253-116">See Also</span></span>  
 [<span data-ttu-id="9a253-117">Tag di commento XML</span><span class="sxs-lookup"><span data-stu-id="9a253-117">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
