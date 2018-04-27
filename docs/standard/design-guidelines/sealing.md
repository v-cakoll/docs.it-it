---
title: sealed
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology: dotnet-standard
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- limiting extensibility
- classes [.NET Framework], sealing
- preventing customization
- sealed classes
ms.assetid: cc42267f-bb7a-427a-845e-df97408528d4
caps.latest.revision: 10
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 8a9ea7fd4f5df08631231db08ba7943a9c131012
ms.sourcegitcommit: 2e8acae16ae802f2d6d04e3ce0a6dbf04e476513
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2018
---
# <a name="sealing"></a>sealed
Una delle funzionalità del Framework orientata a oggetti è che gli sviluppatori possono estendere e personalizzarli in modi imprevisti per le finestre di progettazione di framework. Questa è la potenza e pericolo di progettazione estensibile. Quando si progetta il framework, è pertanto molto importante per progettare con attenzione per l'estensibilità quando si desidera e per limitare l'estendibilità quando è pericoloso.  
  
 L'utilizzo di un meccanismo potente che impedisce l'estendibilità è sealed. È possibile bloccare i singoli membri o classe. Una classe impedisce agli utenti di ereditare dalla classe. Chiusura di un membro impedisce agli utenti di un particolare membro viene sottoposto a override.  
  
 **X non** bloccare classi senza un buon motivo per eseguire questa operazione.  
  
 Chiusura di una classe poiché è possibile considerare uno scenario di estensibilità non è un buon motivo. Gli utenti di Framework come ereditare da classi per vari motivi non prevedibile, ad esempio l'aggiunta di membri di praticità. Vedere [classi non sealed](../../../docs/standard/design-guidelines/unsealed-classes.md) per esempi di motivi non prevedibile gli utenti desiderano ereditare da un tipo.  
  
 Di seguito sono indicati i motivi validi per una classe:  
  
-   La classe è una classe statica. Vedere [progettazione di classi statiche](../../../docs/standard/design-guidelines/static-class.md).  
  
-   La classe archivia i segreti sensibili alla sicurezza in membri protetti ereditati.  
  
-   La classe eredita molti membri virtuali e il costo del rendere sealed li singolarmente annullerebbe i vantaggi di lasciare la classe non sealed.  
  
-   La classe è un attributo che richiede una ricerca di un runtime molto veloce. Gli attributi sealed hanno livelli di prestazioni leggermente superiori rispetto a quelli non sealed. vedere [attributi](../../../docs/standard/design-guidelines/attributes.md).  
  
 **X non** dichiarare membri protetti o virtuali su tipi sealed.  
  
 Per definizione, non è possibile ereditare tipi sealed. Ciò significa che i membri protetti su tipi sealed non possono essere chiamati e metodi virtuali su tipi sealed non possono essere sottoposto a override.  
  
 **✓ Provare a** sealing membri che si esegue l'override.  
  
 I problemi che possono derivare da introduzione membri virtuali (descritto in [membri virtuali](../../../docs/standard/design-guidelines/virtual-members.md)) si applicano a sostituzioni, anche se a un livello leggermente inferiore. Come rendere sealed un override protegge da questi problemi, a partire da quel punto nella gerarchia di ereditarietà.  
  
 *Parti © 2005, 2009 Microsoft Corporation. Tutti i diritti riservati.*  
  
 *State ristampate dall'autorizzazione di Pearson Education, Inc. da [linee guida: convenzioni, idiomi e modelli per le librerie .NET di riutilizzabile, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina e Brad Abrams, pubblicato il 22 ottobre 2008 di Addison-Wesley Professional come parte della serie di sviluppo di Microsoft Windows.*  
  
## <a name="see-also"></a>Vedere anche  
 [Linee guida per la progettazione di Framework](../../../docs/standard/design-guidelines/index.md)  
 [Progettazione finalizzata all'estensibilità](../../../docs/standard/design-guidelines/designing-for-extensibility.md)  
 [Classi non sealed](../../../docs/standard/design-guidelines/unsealed-classes.md)
