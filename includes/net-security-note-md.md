---
ms.openlocfilehash: f01d0a24202ecda7e23cbe925bb6dc8962cb7574
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61750725"
---
> [!CAUTION]
>  Sicurezza dall'accesso di codice e codice parzialmente attendibile  
>   
>  .NET Framework fornisce un meccanismo denominato sicurezza dall'accesso di codice, che consente di applicare vari livelli di attendibilità a codice diverso in esecuzione nella stessa applicazione.  La sicurezza per l'accesso di codice in .NET Framework non deve essere usata come meccanismo per l'applicazione dei limiti di sicurezza in base alla creazione di codice o altri aspetti di identità. Le linee guida sono state modificate per specificare che la sicurezza per l'accesso di codice e il codice SecurityTransparent non saranno supportati come limiti di sicurezza con codice parzialmente attendibile, soprattutto nel caso di codice di origine sconosciuta. Non è consigliabile caricare ed eseguire codice di origine sconosciuta in assenza di misure di sicurezza alternative.  
>   
>  Questi criteri si applicano a tutte le versioni di .NET Framework, ma non alla versione di .NET Framework inclusa in Silverlight.