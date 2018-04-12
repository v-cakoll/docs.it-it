---
title: '&#39; &lt;interfacename&gt;.&lt; MemberName&gt;&#39; è già implementata dalla classe di base &#39;&lt; nomeclassebase&gt;&#39;. Prevista nuova implementazione di &lt;tipo&gt; presuppone'
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc42015
- bc42015
helpviewer_keywords:
- BC42015
ms.assetid: 658c070a-113e-4bd8-b294-12c243191160
caps.latest.revision: 12
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 69884ed567e0046da5cf5c51b3e83e57e890d49f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="39ltinterfacenamegtltmembernamegt39-is-already-implemented-by-the-base-class-39ltbaseclassnamegt39-re-implementation-of-lttypegt-assumed"></a><span data-ttu-id="9c65e-103">&#39; &lt;interfacename&gt;.&lt; MemberName&gt;&#39; è già implementata dalla classe di base &#39;&lt; nomeclassebase&gt;&#39;.</span><span class="sxs-lookup"><span data-stu-id="9c65e-103">&#39;&lt;interfacename&gt;.&lt;membername&gt;&#39; is already implemented by the base class &#39;&lt;baseclassname&gt;&#39;.</span></span> <span data-ttu-id="9c65e-104">Prevista nuova implementazione di &lt;tipo&gt; presuppone</span><span class="sxs-lookup"><span data-stu-id="9c65e-104">Re-implementation of &lt;type&gt; assumed</span></span>
<span data-ttu-id="9c65e-105">Una proprietà, routine o evento in una classe derivata utilizza un `Implements` clausola che specifica un membro di interfaccia che è già implementato nella classe base.</span><span class="sxs-lookup"><span data-stu-id="9c65e-105">A property, procedure, or event in a derived class uses an `Implements` clause specifying an interface member that is already implemented in the base class.</span></span>  
  
 <span data-ttu-id="9c65e-106">Una classe derivata può reimplementare un membro di interfaccia implementato dalla sua classe base.</span><span class="sxs-lookup"><span data-stu-id="9c65e-106">A derived class can reimplement an interface member that is implemented by its base class.</span></span> <span data-ttu-id="9c65e-107">Questo non equivale a eseguire l'override dell'implementazione della classe base.</span><span class="sxs-lookup"><span data-stu-id="9c65e-107">This is not the same as overriding the base class implementation.</span></span> <span data-ttu-id="9c65e-108">Per ulteriori informazioni, vedere [implementa](../../../visual-basic/language-reference/statements/implements-clause.md).</span><span class="sxs-lookup"><span data-stu-id="9c65e-108">For more information, see [Implements](../../../visual-basic/language-reference/statements/implements-clause.md).</span></span>  
  
 <span data-ttu-id="9c65e-109">Per impostazione predefinita, si tratta di un messaggio di avviso.</span><span class="sxs-lookup"><span data-stu-id="9c65e-109">By default, this message is a warning.</span></span> <span data-ttu-id="9c65e-110">Per informazioni su come nascondere gli avvisi o considerarli come errori, vedere [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="9c65e-110">For information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="9c65e-111">**ID errore:** BC42015</span><span class="sxs-lookup"><span data-stu-id="9c65e-111">**Error ID:** BC42015</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="9c65e-112">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="9c65e-112">To correct this error</span></span>  
  
-   <span data-ttu-id="9c65e-113">Se si intende reimplementare il membro di interfaccia, non occorre fare nulla.</span><span class="sxs-lookup"><span data-stu-id="9c65e-113">If you intend to reimplement the interface member, you do not need to take any action.</span></span> <span data-ttu-id="9c65e-114">Codice nella classe derivata accede al membro reimplementato a meno che non si utilizza il `MyBase` (parola chiave) per accedere all'implementazione della classe di base.</span><span class="sxs-lookup"><span data-stu-id="9c65e-114">Code in your derived class accesses the reimplemented member unless you use the `MyBase` keyword to access the base class implementation.</span></span>  
  
-   <span data-ttu-id="9c65e-115">Se non si intende reimplementare il membro di interfaccia, rimuovere la clausola `Implements` dalla dichiarazione di proprietà, routine o evento.</span><span class="sxs-lookup"><span data-stu-id="9c65e-115">If you do not intend to reimplement the interface member, remove the `Implements` clause from the property, procedure, or event declaration.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9c65e-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9c65e-116">See Also</span></span>  
 [<span data-ttu-id="9c65e-117">Interfacce</span><span class="sxs-lookup"><span data-stu-id="9c65e-117">Interfaces</span></span>](../../../visual-basic/programming-guide/language-features/interfaces/index.md)
