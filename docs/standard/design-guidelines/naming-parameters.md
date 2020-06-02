---
title: Denominazione di parametri
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- parameters, names
- names [.NET Framework], parameters
ms.assetid: ca3c956e-725a-441b-b4e3-eab5d472f41c
ms.openlocfilehash: 0d5c5cd144fbae88439ee981fbdb6e30ff487005
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "84290162"
---
# <a name="naming-parameters"></a><span data-ttu-id="d4b6a-102">Denominazione di parametri</span><span class="sxs-lookup"><span data-stu-id="d4b6a-102">Naming Parameters</span></span>
<span data-ttu-id="d4b6a-103">Oltre al motivo più ovvio della leggibilità, è importante seguire le linee guida per i nomi dei parametri, perché i parametri vengono visualizzati nella documentazione e nella finestra di progettazione quando gli strumenti di progettazione visivi forniscono funzionalità IntelliSense e di esplorazione delle classi.</span><span class="sxs-lookup"><span data-stu-id="d4b6a-103">Beyond the obvious reason of readability, it is important to follow the guidelines for parameter names because parameters are displayed in documentation and in the designer when visual design tools provide Intellisense and class browsing functionality.</span></span>

 <span data-ttu-id="d4b6a-104">✔️ utilizzare camelCasing nei nomi dei parametri.</span><span class="sxs-lookup"><span data-stu-id="d4b6a-104">✔️ DO use camelCasing in parameter names.</span></span>

 <span data-ttu-id="d4b6a-105">✔️ utilizzare nomi di parametro descrittivi.</span><span class="sxs-lookup"><span data-stu-id="d4b6a-105">✔️ DO use descriptive parameter names.</span></span>

 <span data-ttu-id="d4b6a-106">✔️ CONSIDERARE l'uso di nomi basati sul significato di un parametro anziché sul tipo del parametro.</span><span class="sxs-lookup"><span data-stu-id="d4b6a-106">✔️ CONSIDER using names based on a parameter’s meaning rather than the parameter’s type.</span></span>

### <a name="naming-operator-overload-parameters"></a><span data-ttu-id="d4b6a-107">Denominazione dei parametri di overload degli operatori</span><span class="sxs-lookup"><span data-stu-id="d4b6a-107">Naming Operator Overload Parameters</span></span>
 <span data-ttu-id="d4b6a-108">✔️ utilizzare `left` e `right` per i nomi dei parametri di overload degli operatori binari se non esiste alcun significato per i parametri.</span><span class="sxs-lookup"><span data-stu-id="d4b6a-108">✔️ DO use `left` and `right` for binary operator overload parameter names if there is no meaning to the parameters.</span></span>

 <span data-ttu-id="d4b6a-109">✔️ utilizzare `value` per i nomi dei parametri di overload dell'operatore unario se non esiste alcun significato per i parametri.</span><span class="sxs-lookup"><span data-stu-id="d4b6a-109">✔️ DO use `value` for unary operator overload parameter names if there is no meaning to the parameters.</span></span>

 <span data-ttu-id="d4b6a-110">✔️ CONSIDERARE nomi significativi per i parametri di overload degli operatori se questa operazione aggiunge un valore significativo.</span><span class="sxs-lookup"><span data-stu-id="d4b6a-110">✔️ CONSIDER meaningful names for operator overload parameters if doing so adds significant value.</span></span>

 <span data-ttu-id="d4b6a-111">❌Non usare abbreviazioni o indici numerici per i nomi dei parametri di overload degli operatori.</span><span class="sxs-lookup"><span data-stu-id="d4b6a-111">❌ DO NOT use abbreviations or numeric indices for operator overload parameter names.</span></span>

 <span data-ttu-id="d4b6a-112">*Parti © 2005, 2009 Microsoft Corporation. Tutti i diritti riservati.*</span><span class="sxs-lookup"><span data-stu-id="d4b6a-112">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>

 <span data-ttu-id="d4b6a-113">*Ristampato con l'autorizzazione di Pearson Education, Inc. da [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2a edizione](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) di Krzysztof Cwalina and Brad Abrams, pubblicato il 22 ottobre 2008 da Addison-Wesley Professional nella collana Microsoft Windows Development Series.*</span><span class="sxs-lookup"><span data-stu-id="d4b6a-113">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>

## <a name="see-also"></a><span data-ttu-id="d4b6a-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d4b6a-114">See also</span></span>

- [<span data-ttu-id="d4b6a-115">Linee guida per la progettazione di Framework</span><span class="sxs-lookup"><span data-stu-id="d4b6a-115">Framework Design Guidelines</span></span>](index.md)
- [<span data-ttu-id="d4b6a-116">Linee guida per la denominazione</span><span class="sxs-lookup"><span data-stu-id="d4b6a-116">Naming Guidelines</span></span>](naming-guidelines.md)
