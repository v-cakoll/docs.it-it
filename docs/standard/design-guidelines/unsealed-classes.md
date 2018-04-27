---
title: Classi non sealed
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology: dotnet-standard
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- classes [.NET Framework], unsealed
- unsealed classes
- inheritance, classes
ms.assetid: 9a3bd505-90f5-4053-9f0d-3cf5fa3d3ebf
caps.latest.revision: 9
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: c798c3cc93f08b77be7d0a5e0d1232d5598aed6b
ms.sourcegitcommit: 2e8acae16ae802f2d6d04e3ce0a6dbf04e476513
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2018
---
# <a name="unsealed-classes"></a>Classi non sealed
Classi sealed non possono essere ereditate da e impediscono l'estensibilità. Al contrario, le classi che possono essere ereditate da sono dette classi non sealed.  
  
 **✓ Provare a** utilizzando classi non sealed con nessuna aggiunti i membri virtuali o protetti come un ottimo modo per fornire a basso costo ancora molto apprezzato estensibilità per un framework.  
  
 Gli sviluppatori spesso necessario ereditare da classi non sealed in modo da aggiungere i membri di praticità, ad esempio l'overload del metodo, nuovi metodi o costruttori personalizzati. Ad esempio, `System.Messaging.MessageQueue` non bloccato e pertanto consente agli utenti di creare code personalizzate tale impostazione predefinita a un percorso di coda specifica o per aggiungere metodi personalizzati che semplificano l'API per scenari specifici.  
  
 Le classi sono non sealed per impostazione predefinita nei linguaggi di programmazione più, e questo è il valore predefinito consigliato per la maggior parte delle classi in Framework. L'estendibilità offerta dal tipi non sealed è molto apprezzato dagli utenti framework e molto costosi da fornire a causa dei costi relativamente basso di test associati a tipi non sealed.  
  
 *Parti © 2005, 2009 Microsoft Corporation. Tutti i diritti riservati.*  
  
 *State ristampate dall'autorizzazione di Pearson Education, Inc. da [linee guida: convenzioni, idiomi e modelli per le librerie .NET di riutilizzabile, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina e Brad Abrams, pubblicato il 22 ottobre 2008 di Addison-Wesley Professional come parte della serie di sviluppo di Microsoft Windows.*  
  
## <a name="see-also"></a>Vedere anche  
 [Linee guida per la progettazione di Framework](../../../docs/standard/design-guidelines/index.md)  
 [Progettazione finalizzata all'estensibilità](../../../docs/standard/design-guidelines/designing-for-extensibility.md)  
 [Sealing](../../../docs/standard/design-guidelines/sealing.md)
