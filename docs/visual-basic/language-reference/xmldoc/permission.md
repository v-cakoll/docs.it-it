---
title: '&lt;autorizzazione&gt; (Visual Basic)'
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- <permission> XML tag
- permission XML tag
ms.assetid: 0edf0500-5cd7-49c0-9255-64c48f972b77
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 67e11998e43a43f92c26eb5f7daa488d288823c8
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="ltpermissiongt-visual-basic"></a><span data-ttu-id="01926-102">&lt;autorizzazione&gt; (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="01926-102">&lt;permission&gt; (Visual Basic)</span></span>
<span data-ttu-id="01926-103">Specifica un'autorizzazione necessaria per il membro.</span><span class="sxs-lookup"><span data-stu-id="01926-103">Specifies a required permission for the member.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="01926-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="01926-104">Syntax</span></span>  
  
```xml  
<permission cref="member">description</permission>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="01926-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="01926-105">Parameters</span></span>  
 `member`  
 <span data-ttu-id="01926-106">Riferimento a un membro o a un campo disponibile per essere chiamato dall'ambiente di compilazione corrente.</span><span class="sxs-lookup"><span data-stu-id="01926-106">A reference to a member or field that is available to be called from the current compilation environment.</span></span> <span data-ttu-id="01926-107">Il compilatore verifica l'esistenza dell'elemento di codice specificato e converte `member` nel nome canonico dell'elemento nel file XML di output.</span><span class="sxs-lookup"><span data-stu-id="01926-107">The compiler checks that the given code element exists and translates `member` to the canonical element name in the output XML.</span></span> <span data-ttu-id="01926-108">Racchiudere `member` tra virgolette ("").</span><span class="sxs-lookup"><span data-stu-id="01926-108">Enclose `member` in quotation marks (" ").</span></span>  
  
 `description`  
 <span data-ttu-id="01926-109">Descrizione dell'accesso al membro.</span><span class="sxs-lookup"><span data-stu-id="01926-109">A description of the access to the member.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="01926-110">Note</span><span class="sxs-lookup"><span data-stu-id="01926-110">Remarks</span></span>  
 <span data-ttu-id="01926-111">Utilizzare il `<permission>` tag per documentare l'accesso di un membro.</span><span class="sxs-lookup"><span data-stu-id="01926-111">Use the `<permission>` tag to document the access of a member.</span></span> <span data-ttu-id="01926-112">Utilizzare la <xref:System.Security.PermissionSet> classe per specificare l'accesso a un membro.</span><span class="sxs-lookup"><span data-stu-id="01926-112">Use the <xref:System.Security.PermissionSet> class to specify access to a member.</span></span>  
  
 <span data-ttu-id="01926-113">Compilare con [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) per elaborare i commenti relativi alla documentazione in un file.</span><span class="sxs-lookup"><span data-stu-id="01926-113">Compile with [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="01926-114">Esempio</span><span class="sxs-lookup"><span data-stu-id="01926-114">Example</span></span>  
 <span data-ttu-id="01926-115">Questo esempio viene utilizzato il `<permission>` tag per descrivere il <xref:System.Security.Permissions.FileIOPermission> richiesto dal `ReadFile` metodo.</span><span class="sxs-lookup"><span data-stu-id="01926-115">This example uses the `<permission>` tag to describe that the <xref:System.Security.Permissions.FileIOPermission> is required by the `ReadFile` method.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#7](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/permission_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="01926-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="01926-116">See Also</span></span>  
 [<span data-ttu-id="01926-117">Tag di commento XML</span><span class="sxs-lookup"><span data-stu-id="01926-117">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)
