---
title: sealed
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- limiting extensibility
- classes [.NET Framework], sealing
- preventing customization
- sealed classes
ms.assetid: cc42267f-bb7a-427a-845e-df97408528d4
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6d8c445de44a69f6c0cb1eaefa0e59d682288318
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/14/2018
ms.locfileid: "45614008"
---
# <a name="sealing"></a>sealed
Una delle funzionalità orientate a oggetti Framework è che gli sviluppatori possono estendere e personalizzarli in modi non previsti per i progettisti del framework. Questa è la potenza e pericolo di progettazione estendibile. Quando si progetta il tuo framework, è quindi molto importante per progettare con attenzione per l'estensibilità quando lo si desidera e per limitare l'estendibilità è pericoloso.  
  
 Una soluzione efficace che impedisce l'estendibilità è sealed. È possibile applicare il seal classe o singoli membri. Una classe impedisce agli utenti di ereditare dalla classe. Come rendere sealed un membro impedisce agli utenti di eseguire l'override di un membro specifico.  
  
 **X DO NOT** bloccare classi senza un buon motivo per eseguire questa operazione.  
  
 Come rendere sealed una classe poiché è possibile pensare a uno scenario di estensibilità non è una buona ragione. Gli utenti di Framework, ad esempio ereditare dalle classi per vari motivi non prevedibile, quali l'aggiunta di membri di praticità. Visualizzare [classi non sealed](../../../docs/standard/design-guidelines/unsealed-classes.md) per alcuni dei motivi non prevedibile degli utenti desiderano ereditare da un tipo.  
  
 Buone ragioni per una classe includono quanto segue:  
  
-   La classe è una classe statica. Visualizzare [progettazione di classi statiche](../../../docs/standard/design-guidelines/static-class.md).  
  
-   La classe archivia i segreti sensibili alla sicurezza in membri protetti ereditati.  
  
-   La classe eredita molte membri virtuali e il costo del sealing li singolarmente sarebbe superano i vantaggi di lasciare la classe non sealed.  
  
-   La classe è un attributo che richiede la ricerca di runtime molto veloce. Gli attributi sealed hanno livelli di prestazioni leggermente superiori rispetto a quelli non sealed. visualizzare [attributi](../../../docs/standard/design-guidelines/attributes.md).  
  
 **X DO NOT** dichiarare membri protetti o virtuali su tipi sealed.  
  
 Per definizione, tipi sealed non possono essere ereditati da. Ciò significa che i membri protetti nei tipi sealed non possono essere chiamati e metodi virtuali nei tipi sealed non possono essere sottoposto a override.  
  
 **✓ CONSIDER** sealing membri che si esegue l'override.  
  
 I problemi derivanti dall'introduzione a membri virtuali (descritto in [membri virtuali](../../../docs/standard/design-guidelines/virtual-members.md)) si applicano agli override, anche se a un livello leggermente inferiore. Come rendere sealed un override ci consente di nascondere questi problemi a partire da quel punto nella gerarchia di ereditarietà.  
  
 *Parti protette da copyright © 2005, 2009 Microsoft Corporation. Tutti i diritti riservati.*  
  
 *Ristampato con l'autorizzazione di Pearson Education, Inc. da [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2a edizione](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) di Krzysztof Cwalina and Brad Abrams, pubblicato il 22 ottobre 2008 da Addison-Wesley Professional nella collana Microsoft Windows Development Series.*  
  
## <a name="see-also"></a>Vedere anche

- [Linee guida per la progettazione di Framework](../../../docs/standard/design-guidelines/index.md)  
- [Progettazione finalizzata all'estensibilità](../../../docs/standard/design-guidelines/designing-for-extensibility.md)  
- [Classi non sealed](../../../docs/standard/design-guidelines/unsealed-classes.md)
