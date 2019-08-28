---
ms.openlocfilehash: f70452cbadc8927521f0fcfda693586c277e4d0f
ms.sourcegitcommit: 581ab03291e91983459e56e40ea8d97b5189227e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2019
ms.locfileid: "70041150"
---
> [!CAUTION]
> <span data-ttu-id="50a81-101">Sicurezza dall'accesso di codice e codice parzialmente attendibile</span><span class="sxs-lookup"><span data-stu-id="50a81-101">Code Access Security and Partially Trusted Code</span></span>
>
> <span data-ttu-id="50a81-102">.NET Framework fornisce un meccanismo denominato sicurezza dall'accesso di codice, che consente di applicare vari livelli di attendibilità a codice diverso in esecuzione nella stessa applicazione.</span><span class="sxs-lookup"><span data-stu-id="50a81-102">The .NET Framework provides a mechanism for the enforcement of varying levels of trust on different code running in the same application called Code Access Security (CAS).</span></span>  <span data-ttu-id="50a81-103">La sicurezza per l'accesso di codice in .NET Framework non deve essere usata come meccanismo per l'applicazione dei limiti di sicurezza in base alla creazione di codice o altri aspetti di identità.</span><span class="sxs-lookup"><span data-stu-id="50a81-103">Code Access Security in .NET Framework should not  be used as a mechanism for enforcing security boundaries based on code origination or other identity aspects.</span></span> <span data-ttu-id="50a81-104">Le linee guida sono state modificate per specificare che la sicurezza per l'accesso di codice e il codice SecurityTransparent non saranno supportati come limiti di sicurezza con codice parzialmente attendibile, soprattutto nel caso di codice di origine sconosciuta.</span><span class="sxs-lookup"><span data-stu-id="50a81-104">We are updating our guidance to reflect that Code Access Security and Security-Transparent Code will not be supported as a security boundary with partially trusted code, especially code of unknown origin.</span></span> <span data-ttu-id="50a81-105">Non è consigliabile caricare ed eseguire codice di origine sconosciuta in assenza di misure di sicurezza alternative.</span><span class="sxs-lookup"><span data-stu-id="50a81-105">We advise against loading and executing code of unknown origins without putting alternative security measures in place.</span></span>
>
> <span data-ttu-id="50a81-106">Questi criteri si applicano a tutte le versioni di .NET Framework, ma non alla versione di .NET Framework inclusa in Silverlight.</span><span class="sxs-lookup"><span data-stu-id="50a81-106">This policy applies to all versions of .NET Framework, but does not apply to the .NET Framework included in Silverlight.</span></span>
