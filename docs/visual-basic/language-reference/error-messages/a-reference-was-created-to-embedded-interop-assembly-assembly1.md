---
title: È stato creato un riferimento all'assembly di interoperabilità incorporato '<assembly1>' a causa di un riferimento indiretto a tale assembly dall'assembly '<assembly2>'
ms.date: 07/20/2015
f1_keywords:
- vbc40059
- bc40059
helpviewer_keywords:
- VBC40059
- BC40059
ms.assetid: 520e39cb-8ab6-46f5-aa00-08afd51b4b7c
ms.openlocfilehash: 058aa4891d05147756290affd60ea5fb260c33ef
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/30/2019
ms.locfileid: "55262952"
---
# <a name="a-reference-was-created-to-embedded-interop-assembly-assembly1-because-of-an-indirect-reference-to-that-assembly-from-assembly-assembly2"></a><span data-ttu-id="bd847-102">È stato creato un riferimento all'assembly di interoperabilità incorporato '\<assembly1 >' a causa di un riferimento indiretto a tale assembly dall'assembly '\<assembly2 >'</span><span class="sxs-lookup"><span data-stu-id="bd847-102">A reference was created to embedded interop assembly '\<assembly1>' because of an indirect reference to that assembly from assembly '\<assembly2>'</span></span>
<span data-ttu-id="bd847-103">È stato creato un riferimento all'assembly di interoperabilità incorporato '\<assembly1>' a causa di un riferimento indiretto a tale assembly creato dall'assembly '\<assembly2>'.</span><span class="sxs-lookup"><span data-stu-id="bd847-103">A reference was created to embedded interop assembly '\<assembly1>' because of an indirect reference to that assembly from assembly '\<assembly2>'.</span></span> <span data-ttu-id="bd847-104">Provare a modificare la proprietà 'Incorpora tipi di interoperabilità' in un assembly.</span><span class="sxs-lookup"><span data-stu-id="bd847-104">Consider changing the 'Embed Interop Types' property on either assembly.</span></span>  
  
 <span data-ttu-id="bd847-105">È stato aggiunto un riferimento a un assembly (assembly1) con la proprietà `Embed Interop Types` impostata su `True`.</span><span class="sxs-lookup"><span data-stu-id="bd847-105">You have added a reference to an assembly (assembly1) that has the `Embed Interop Types` property set to `True`.</span></span> <span data-ttu-id="bd847-106">Si dà così istruzione al compilatore di incorporare le informazioni sui tipi di interoperabilità da tale assembly.</span><span class="sxs-lookup"><span data-stu-id="bd847-106">This instructs the compiler to embed interop type information from that assembly.</span></span> <span data-ttu-id="bd847-107">Il compilatore non può tuttavia incorporare le informazioni sui tipi di interoperabilità da tale assembly perché anche un altro assembly a cui si fa riferimento (assembly2) fa riferimento a tale assembly (assembly1) e ha la proprietà `Embed Interop Types` impostata su `False`.</span><span class="sxs-lookup"><span data-stu-id="bd847-107">However, the compiler cannot embed interop type information from that assembly because another assembly that you have referenced (assembly2) also references that assembly (assembly1) and has the `Embed Interop Types` property set to `False`.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="bd847-108">L'impostazione della proprietà `Embed Interop Types` per un riferimento a un assembly su `True` equivale a fare riferimento all'assembly usando l'opzione del compilatore della riga di comando `/link`.</span><span class="sxs-lookup"><span data-stu-id="bd847-108">Setting the `Embed Interop Types` property on an assembly reference to `True` is equivalent to referencing the assembly by using the `/link` option for the command-line compiler.</span></span>  
  
 <span data-ttu-id="bd847-109">**ID errore:** BC40059</span><span class="sxs-lookup"><span data-stu-id="bd847-109">**Error ID:** BC40059</span></span>  
  
### <a name="to-address-this-warning"></a><span data-ttu-id="bd847-110">Per risolvere questo avviso</span><span class="sxs-lookup"><span data-stu-id="bd847-110">To address this warning</span></span>  
  
-   <span data-ttu-id="bd847-111">Per incorporare le informazioni sui tipi di interoperabilità per entrambi gli assembly, impostare la proprietà `Embed Interop Types` per tutti i riferimenti a assembly1 su `True`.</span><span class="sxs-lookup"><span data-stu-id="bd847-111">To embed interop type information for both assemblies, set the `Embed Interop Types` property on all references to assembly1 to `True`.</span></span>  
  
-   <span data-ttu-id="bd847-112">Per rimuovere l'avviso, è possibile impostare la proprietà `Embed Interop Types` di assembly1 su `False`.</span><span class="sxs-lookup"><span data-stu-id="bd847-112">To remove the warning, you can set the `Embed Interop Types` property of assembly1 to `False`.</span></span> <span data-ttu-id="bd847-113">In questo caso, le informazioni sul tipo di interoperabilità viene forniti da un assembly di interoperabilità primario (PIA).</span><span class="sxs-lookup"><span data-stu-id="bd847-113">In this case, interop type information is provided by a primary interop assembly (PIA).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bd847-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bd847-114">See also</span></span>
- [<span data-ttu-id="bd847-115">/link (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="bd847-115">/link (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/link.md)
- [<span data-ttu-id="bd847-116">Interoperabilità con codice non gestito</span><span class="sxs-lookup"><span data-stu-id="bd847-116">Interoperating with Unmanaged Code</span></span>](../../../framework/interop/index.md)
