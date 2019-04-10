---
title: Impossibile fare riferimento a '<name>' perché è un membro del campo di valori '<name>' della classe '<classname>' che ha 'System.MarshalByRefObject' come classe base
ms.date: 07/20/2015
f1_keywords:
- vbc30310
- bc30310
helpviewer_keywords:
- BC30310
ms.assetid: 2aeb8872-7c87-4f01-98ef-9714ba3eebbe
ms.openlocfilehash: 78b0a3131b6e77ed257f200523ecebd4dfce3691
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2019
ms.locfileid: "59316544"
---
# <a name="cannot-refer-to-name-because-it-is-a-member-of-the-value-typed-field-name-of-class-classname-which-has-systemmarshalbyrefobject-as-a-base-class"></a><span data-ttu-id="c73a2-102">Impossibile fare riferimento a '\<nome >' perché è un membro del campo valori '\<nome >' della classe\<NomeClasse >' che ha 'System. MarshalByRefObject' come classe di base</span><span class="sxs-lookup"><span data-stu-id="c73a2-102">Cannot refer to '\<name>' because it is a member of the value-typed field '\<name>' of class '\<classname>' which has 'System.MarshalByRefObject' as a base class</span></span>
<span data-ttu-id="c73a2-103">Il `System.MarshalByRefObject` classe consente alle applicazioni che supportano l'accesso remoto a oggetti attraverso limiti di dominio.</span><span class="sxs-lookup"><span data-stu-id="c73a2-103">The `System.MarshalByRefObject` class enables applications that support remote access to objects across application domain boundaries.</span></span> <span data-ttu-id="c73a2-104">I tipi devono ereditare dal `MarshalByRejectObject` classe quando viene utilizzato il tipo superando i limiti di dominio di applicazione.</span><span class="sxs-lookup"><span data-stu-id="c73a2-104">Types must inherit from the `MarshalByRejectObject` class when the type is used across application domain boundaries.</span></span> <span data-ttu-id="c73a2-105">Lo stato dell'oggetto non deve essere copiato perché i membri dell'oggetto non sono utilizzabili all'esterno del dominio applicazione in cui sono stati creati.</span><span class="sxs-lookup"><span data-stu-id="c73a2-105">The state of the object must not be copied because the members of the object are not usable outside the application domain in which they were created.</span></span>  
  
 <span data-ttu-id="c73a2-106">**ID errore:** BC30310</span><span class="sxs-lookup"><span data-stu-id="c73a2-106">**Error ID:** BC30310</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="c73a2-107">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="c73a2-107">To correct this error</span></span>  
  
1. <span data-ttu-id="c73a2-108">Verificare il riferimento per assicurarsi che il membro a cui si fa riferimento è valido.</span><span class="sxs-lookup"><span data-stu-id="c73a2-108">Check the reference to make sure the member being referred to is valid.</span></span>  
  
2. <span data-ttu-id="c73a2-109">Qualificare in modo esplicito il membro con il `Me` (parola chiave).</span><span class="sxs-lookup"><span data-stu-id="c73a2-109">Explicitly qualify the member with the `Me` keyword.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c73a2-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c73a2-110">See also</span></span>

- <xref:System.MarshalByRefObject>
- [<span data-ttu-id="c73a2-111">Istruzione Dim</span><span class="sxs-lookup"><span data-stu-id="c73a2-111">Dim Statement</span></span>](../../../visual-basic/language-reference/statements/dim-statement.md)
