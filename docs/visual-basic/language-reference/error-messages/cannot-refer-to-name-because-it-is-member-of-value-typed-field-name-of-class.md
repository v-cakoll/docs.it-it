---
title: Non è possibile fare riferimento a &#39; &lt;nome&gt; &#39; perché è un membro del campo valori &#39; &lt;nome&gt; &#39; della classe &#39; &lt;classname&gt; &#39;che dispone di &#39;System. MarshalByRefObject&#39; come classe di base
ms.date: 07/20/2015
f1_keywords:
- vbc30310
- bc30310
helpviewer_keywords:
- BC30310
ms.assetid: 2aeb8872-7c87-4f01-98ef-9714ba3eebbe
ms.openlocfilehash: f44d33c9d51148e6bbcfbf5db4dbc115101df1f1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33586347"
---
# <a name="cannot-refer-to-39ltnamegt39-because-it-is-a-member-of-the-value-typed-field-39ltnamegt39-of-class-39ltclassnamegt39-which-has-39systemmarshalbyrefobject39-as-a-base-class"></a><span data-ttu-id="7c33d-102">Non è possibile fare riferimento a &#39; &lt;nome&gt; &#39; perché è un membro del campo valori &#39; &lt;nome&gt; &#39; della classe &#39; &lt;classname&gt; &#39;che dispone di &#39;System. MarshalByRefObject&#39; come classe di base</span><span class="sxs-lookup"><span data-stu-id="7c33d-102">Cannot refer to &#39;&lt;name&gt;&#39; because it is a member of the value-typed field &#39;&lt;name&gt;&#39; of class &#39;&lt;classname&gt;&#39; which has &#39;System.MarshalByRefObject&#39; as a base class</span></span>
<span data-ttu-id="7c33d-103">La `System.MarshalByRefObject` classe consente alle applicazioni che supportano l'accesso remoto agli oggetti limiti del dominio applicazione.</span><span class="sxs-lookup"><span data-stu-id="7c33d-103">The `System.MarshalByRefObject` class enables applications that support remote access to objects across application domain boundaries.</span></span> <span data-ttu-id="7c33d-104">I tipi devono ereditare dalla `MarshalByRejectObject` classe quando i limiti del dominio applicazione viene utilizzato il tipo.</span><span class="sxs-lookup"><span data-stu-id="7c33d-104">Types must inherit from the `MarshalByRejectObject` class when the type is used across application domain boundaries.</span></span> <span data-ttu-id="7c33d-105">Lo stato dell'oggetto non deve essere copiato perché i membri dell'oggetto non sono utilizzabili all'esterno del dominio applicazione in cui sono stati creati.</span><span class="sxs-lookup"><span data-stu-id="7c33d-105">The state of the object must not be copied because the members of the object are not usable outside the application domain in which they were created.</span></span>  
  
 <span data-ttu-id="7c33d-106">**ID errore:** BC30310</span><span class="sxs-lookup"><span data-stu-id="7c33d-106">**Error ID:** BC30310</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="7c33d-107">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="7c33d-107">To correct this error</span></span>  
  
1.  <span data-ttu-id="7c33d-108">Verificare il riferimento per assicurarsi che il membro a cui si fa riferimento è valido.</span><span class="sxs-lookup"><span data-stu-id="7c33d-108">Check the reference to make sure the member being referred to is valid.</span></span>  
  
2.  <span data-ttu-id="7c33d-109">Qualificare in modo esplicito il membro con il `Me` (parola chiave).</span><span class="sxs-lookup"><span data-stu-id="7c33d-109">Explicitly qualify the member with the `Me` keyword.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7c33d-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7c33d-110">See Also</span></span>  
 <xref:System.MarshalByRefObject>  
 [<span data-ttu-id="7c33d-111">Istruzione Dim</span><span class="sxs-lookup"><span data-stu-id="7c33d-111">Dim Statement</span></span>](../../../visual-basic/language-reference/statements/dim-statement.md)
