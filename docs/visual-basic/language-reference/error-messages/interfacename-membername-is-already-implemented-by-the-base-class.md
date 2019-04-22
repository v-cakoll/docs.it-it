---
title: "'<interfacename>. <membername>'è già implementata dalla classe base'<baseclassname>'. Prevista nuova implementazione di <type> presuppone"
ms.date: 07/20/2015
f1_keywords:
- vbc42015
- bc42015
helpviewer_keywords:
- BC42015
ms.assetid: 658c070a-113e-4bd8-b294-12c243191160
ms.openlocfilehash: 64bd7771820c2a4073350b7a5189d3a32c4775be
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "58832364"
---
# <a name="interfacenamemembername-is-already-implemented-by-the-base-class-baseclassname-re-implementation-of-type-assumed"></a><span data-ttu-id="e3926-103">'\<nomeinterfaccia >. \<nomeMembro >' è già implementata della classe di base\<nomeclassebase >'.</span><span class="sxs-lookup"><span data-stu-id="e3926-103">'\<interfacename>.\<membername>' is already implemented by the base class '\<baseclassname>'.</span></span> <span data-ttu-id="e3926-104">Prevista nuova implementazione di \<tipo > si presuppone che</span><span class="sxs-lookup"><span data-stu-id="e3926-104">Re-implementation of \<type> assumed</span></span>
<span data-ttu-id="e3926-105">Una proprietà, routine o evento in una classe derivata Usa un `Implements` clausola che specifica un membro di interfaccia che è già implementato nella classe di base.</span><span class="sxs-lookup"><span data-stu-id="e3926-105">A property, procedure, or event in a derived class uses an `Implements` clause specifying an interface member that is already implemented in the base class.</span></span>  
  
 <span data-ttu-id="e3926-106">Una classe derivata può reimplementare un membro di interfaccia implementato dalla sua classe base.</span><span class="sxs-lookup"><span data-stu-id="e3926-106">A derived class can reimplement an interface member that is implemented by its base class.</span></span> <span data-ttu-id="e3926-107">Questo non equivale a eseguire l'override dell'implementazione della classe base.</span><span class="sxs-lookup"><span data-stu-id="e3926-107">This is not the same as overriding the base class implementation.</span></span> <span data-ttu-id="e3926-108">Per altre informazioni, vedere [Implements](../../../visual-basic/language-reference/statements/implements-clause.md).</span><span class="sxs-lookup"><span data-stu-id="e3926-108">For more information, see [Implements](../../../visual-basic/language-reference/statements/implements-clause.md).</span></span>  
  
 <span data-ttu-id="e3926-109">Per impostazione predefinita, si tratta di un messaggio di avviso.</span><span class="sxs-lookup"><span data-stu-id="e3926-109">By default, this message is a warning.</span></span> <span data-ttu-id="e3926-110">Per informazioni su come nascondere gli avvisi o considerarli come errori, vedere [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="e3926-110">For information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="e3926-111">**ID errore:** BC42015</span><span class="sxs-lookup"><span data-stu-id="e3926-111">**Error ID:** BC42015</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="e3926-112">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="e3926-112">To correct this error</span></span>  
  
-   <span data-ttu-id="e3926-113">Se si intende reimplementare il membro di interfaccia, non occorre fare nulla.</span><span class="sxs-lookup"><span data-stu-id="e3926-113">If you intend to reimplement the interface member, you do not need to take any action.</span></span> <span data-ttu-id="e3926-114">Codice della classe derivata accede al membro reimplementato a meno che non si utilizza il `MyBase` una parola chiave per accedere all'implementazione della classe di base.</span><span class="sxs-lookup"><span data-stu-id="e3926-114">Code in your derived class accesses the reimplemented member unless you use the `MyBase` keyword to access the base class implementation.</span></span>  
  
-   <span data-ttu-id="e3926-115">Se non si intende reimplementare il membro di interfaccia, rimuovere la clausola `Implements` dalla dichiarazione di proprietà, routine o evento.</span><span class="sxs-lookup"><span data-stu-id="e3926-115">If you do not intend to reimplement the interface member, remove the `Implements` clause from the property, procedure, or event declaration.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e3926-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e3926-116">See also</span></span>

- [<span data-ttu-id="e3926-117">Interfacce</span><span class="sxs-lookup"><span data-stu-id="e3926-117">Interfaces</span></span>](../../../visual-basic/programming-guide/language-features/interfaces/index.md)
