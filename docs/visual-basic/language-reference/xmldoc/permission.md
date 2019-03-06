---
title: <permission> (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- <permission> XML tag
- permission XML tag
ms.assetid: 0edf0500-5cd7-49c0-9255-64c48f972b77
ms.openlocfilehash: d8fe70445b2a2500f99a0156604238665b7bbd1c
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57473500"
---
# <a name="permission-visual-basic"></a><span data-ttu-id="d04ca-102">\<autorizzazione > (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d04ca-102">\<permission> (Visual Basic)</span></span>
<span data-ttu-id="d04ca-103">Specifica un'autorizzazione necessaria per il membro.</span><span class="sxs-lookup"><span data-stu-id="d04ca-103">Specifies a required permission for the member.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d04ca-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d04ca-104">Syntax</span></span>  
  
```xml  
<permission cref="member">description</permission>  
```  
  
## <a name="parameters"></a><span data-ttu-id="d04ca-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="d04ca-105">Parameters</span></span>  
 `member`  
 <span data-ttu-id="d04ca-106">Riferimento a un membro o a un campo disponibile per essere chiamato dall'ambiente di compilazione corrente.</span><span class="sxs-lookup"><span data-stu-id="d04ca-106">A reference to a member or field that is available to be called from the current compilation environment.</span></span> <span data-ttu-id="d04ca-107">Il compilatore verifica l'esistenza dell'elemento di codice specificato e converte `member` nel nome canonico dell'elemento nel file XML di output.</span><span class="sxs-lookup"><span data-stu-id="d04ca-107">The compiler checks that the given code element exists and translates `member` to the canonical element name in the output XML.</span></span> <span data-ttu-id="d04ca-108">Racchiudere `member` racchiuso tra virgolette ("").</span><span class="sxs-lookup"><span data-stu-id="d04ca-108">Enclose `member` in quotation marks (" ").</span></span>  
  
 `description`  
 <span data-ttu-id="d04ca-109">Descrizione dell'accesso al membro.</span><span class="sxs-lookup"><span data-stu-id="d04ca-109">A description of the access to the member.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d04ca-110">Note</span><span class="sxs-lookup"><span data-stu-id="d04ca-110">Remarks</span></span>  
 <span data-ttu-id="d04ca-111">Usare il `<permission>` tag per documentare l'accesso di un membro.</span><span class="sxs-lookup"><span data-stu-id="d04ca-111">Use the `<permission>` tag to document the access of a member.</span></span> <span data-ttu-id="d04ca-112">Usare il <xref:System.Security.PermissionSet> classe per specificare l'accesso a un membro.</span><span class="sxs-lookup"><span data-stu-id="d04ca-112">Use the <xref:System.Security.PermissionSet> class to specify access to a member.</span></span>  
  
 <span data-ttu-id="d04ca-113">Compilare con [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) per elaborare i commenti relativi alla documentazione in un file.</span><span class="sxs-lookup"><span data-stu-id="d04ca-113">Compile with [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d04ca-114">Esempio</span><span class="sxs-lookup"><span data-stu-id="d04ca-114">Example</span></span>  
 <span data-ttu-id="d04ca-115">Questo esempio Usa la `<permission>` tag per descrivere che il <xref:System.Security.Permissions.FileIOPermission> richiesto dal `ReadFile` (metodo).</span><span class="sxs-lookup"><span data-stu-id="d04ca-115">This example uses the `<permission>` tag to describe that the <xref:System.Security.Permissions.FileIOPermission> is required by the `ReadFile` method.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#7)]  
  
## <a name="see-also"></a><span data-ttu-id="d04ca-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d04ca-116">See also</span></span>
- [<span data-ttu-id="d04ca-117">Tag di commento XML</span><span class="sxs-lookup"><span data-stu-id="d04ca-117">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
