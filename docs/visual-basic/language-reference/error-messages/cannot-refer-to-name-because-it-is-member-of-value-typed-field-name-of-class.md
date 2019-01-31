---
title: Impossibile fare riferimento a '<name>' perché è un membro del campo di valori '<name>' della classe '<classname>' che ha 'System.MarshalByRefObject' come classe base
ms.date: 07/20/2015
f1_keywords:
- vbc30310
- bc30310
helpviewer_keywords:
- BC30310
ms.assetid: 2aeb8872-7c87-4f01-98ef-9714ba3eebbe
ms.openlocfilehash: c29d3def2299dc1d7e3b084b3408b3f919addc63
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/30/2019
ms.locfileid: "55279585"
---
# <a name="cannot-refer-to-name-because-it-is-a-member-of-the-value-typed-field-name-of-class-classname-which-has-systemmarshalbyrefobject-as-a-base-class"></a><span data-ttu-id="698a6-102">Impossibile fare riferimento a '\<nome >' perché è un membro del campo valori '\<nome >' della classe\<NomeClasse >' che ha 'System. MarshalByRefObject' come classe di base</span><span class="sxs-lookup"><span data-stu-id="698a6-102">Cannot refer to '\<name>' because it is a member of the value-typed field '\<name>' of class '\<classname>' which has 'System.MarshalByRefObject' as a base class</span></span>
<span data-ttu-id="698a6-103">Il `System.MarshalByRefObject` classe consente alle applicazioni che supportano l'accesso remoto a oggetti attraverso limiti di dominio.</span><span class="sxs-lookup"><span data-stu-id="698a6-103">The `System.MarshalByRefObject` class enables applications that support remote access to objects across application domain boundaries.</span></span> <span data-ttu-id="698a6-104">I tipi devono ereditare dal `MarshalByRejectObject` classe quando viene utilizzato il tipo superando i limiti di dominio di applicazione.</span><span class="sxs-lookup"><span data-stu-id="698a6-104">Types must inherit from the `MarshalByRejectObject` class when the type is used across application domain boundaries.</span></span> <span data-ttu-id="698a6-105">Lo stato dell'oggetto non deve essere copiato perché i membri dell'oggetto non sono utilizzabili all'esterno del dominio applicazione in cui sono stati creati.</span><span class="sxs-lookup"><span data-stu-id="698a6-105">The state of the object must not be copied because the members of the object are not usable outside the application domain in which they were created.</span></span>  
  
 <span data-ttu-id="698a6-106">**ID errore:** BC30310</span><span class="sxs-lookup"><span data-stu-id="698a6-106">**Error ID:** BC30310</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="698a6-107">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="698a6-107">To correct this error</span></span>  
  
1.  <span data-ttu-id="698a6-108">Verificare il riferimento per assicurarsi che il membro a cui si fa riferimento è valido.</span><span class="sxs-lookup"><span data-stu-id="698a6-108">Check the reference to make sure the member being referred to is valid.</span></span>  
  
2.  <span data-ttu-id="698a6-109">Qualificare in modo esplicito il membro con il `Me` (parola chiave).</span><span class="sxs-lookup"><span data-stu-id="698a6-109">Explicitly qualify the member with the `Me` keyword.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="698a6-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="698a6-110">See also</span></span>
- <xref:System.MarshalByRefObject>
- [<span data-ttu-id="698a6-111">Istruzione Dim</span><span class="sxs-lookup"><span data-stu-id="698a6-111">Dim Statement</span></span>](../../../visual-basic/language-reference/statements/dim-statement.md)
