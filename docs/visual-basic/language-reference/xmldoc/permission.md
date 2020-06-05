---
title: <permission>
ms.date: 07/20/2015
helpviewer_keywords:
- <permission> XML tag
- permission XML tag
ms.assetid: 0edf0500-5cd7-49c0-9255-64c48f972b77
ms.openlocfilehash: b3acec04060367a0b9e54b19c0106644d028357b
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84400034"
---
# <a name="permission-visual-basic"></a><span data-ttu-id="36727-101">\<permission> (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="36727-101">\<permission> (Visual Basic)</span></span>
<span data-ttu-id="36727-102">Specifica un'autorizzazione necessaria per il membro.</span><span class="sxs-lookup"><span data-stu-id="36727-102">Specifies a required permission for the member.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="36727-103">Sintassi</span><span class="sxs-lookup"><span data-stu-id="36727-103">Syntax</span></span>  
  
```xml  
<permission cref="member">description</permission>  
```  
  
## <a name="parameters"></a><span data-ttu-id="36727-104">Parametri</span><span class="sxs-lookup"><span data-stu-id="36727-104">Parameters</span></span>  
 `member`  
 <span data-ttu-id="36727-105">Riferimento a un membro o a un campo disponibile per essere chiamato dall'ambiente di compilazione corrente.</span><span class="sxs-lookup"><span data-stu-id="36727-105">A reference to a member or field that is available to be called from the current compilation environment.</span></span> <span data-ttu-id="36727-106">Il compilatore verifica l'esistenza dell'elemento di codice specificato e converte `member` nel nome canonico dell'elemento nel file XML di output.</span><span class="sxs-lookup"><span data-stu-id="36727-106">The compiler checks that the given code element exists and translates `member` to the canonical element name in the output XML.</span></span> <span data-ttu-id="36727-107">Racchiude `member` tra virgolette ("").</span><span class="sxs-lookup"><span data-stu-id="36727-107">Enclose `member` in quotation marks (" ").</span></span>  
  
 `description`  
 <span data-ttu-id="36727-108">Descrizione dell'accesso al membro.</span><span class="sxs-lookup"><span data-stu-id="36727-108">A description of the access to the member.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="36727-109">Commenti</span><span class="sxs-lookup"><span data-stu-id="36727-109">Remarks</span></span>  
 <span data-ttu-id="36727-110">Usare il `<permission>` tag per documentare l'accesso di un membro.</span><span class="sxs-lookup"><span data-stu-id="36727-110">Use the `<permission>` tag to document the access of a member.</span></span> <span data-ttu-id="36727-111">Utilizzare la <xref:System.Security.PermissionSet> classe per specificare l'accesso a un membro.</span><span class="sxs-lookup"><span data-stu-id="36727-111">Use the <xref:System.Security.PermissionSet> class to specify access to a member.</span></span>  
  
 <span data-ttu-id="36727-112">Compilare con [-doc](../../reference/command-line-compiler/doc.md) per elaborare i commenti relativi alla documentazione in un file.</span><span class="sxs-lookup"><span data-stu-id="36727-112">Compile with [-doc](../../reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="36727-113">Esempio</span><span class="sxs-lookup"><span data-stu-id="36727-113">Example</span></span>  
 <span data-ttu-id="36727-114">Questo esempio usa il `<permission>` tag per descrivere che <xref:System.Security.Permissions.FileIOPermission> è richiesto dal `ReadFile` metodo.</span><span class="sxs-lookup"><span data-stu-id="36727-114">This example uses the `<permission>` tag to describe that the <xref:System.Security.Permissions.FileIOPermission> is required by the `ReadFile` method.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#7)]  
  
## <a name="see-also"></a><span data-ttu-id="36727-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="36727-115">See also</span></span>

- [<span data-ttu-id="36727-116">Tag di commento XML</span><span class="sxs-lookup"><span data-stu-id="36727-116">XML Comment Tags</span></span>](index.md)
