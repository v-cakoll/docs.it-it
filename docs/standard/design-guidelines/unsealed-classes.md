---
title: Classi non sealed
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- classes [.NET Framework], unsealed
- unsealed classes
- inheritance, classes
ms.assetid: 9a3bd505-90f5-4053-9f0d-3cf5fa3d3ebf
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ef0f1c4c9b2d1928d6f96d62ab12df9786756498
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/06/2018
ms.locfileid: "43891377"
---
# <a name="unsealed-classes"></a>Classi non sealed
Le classi sealed non possono essere ereditate da, e consentirne l'estendibilità. Al contrario, le classi che possono essere ereditate da vengono denominate classi non sealed.  
  
 **✓ CONSIDER** utilizzando classi non sealed con nessuna aggiunti i membri virtuali o protetti come un ottimo modo per fornire a basso costo ancora molto apprezzato estensibilità per un framework.  
  
 Gli sviluppatori spesso vogliono ereditare da classi non sealed in modo da aggiungere i membri di praticità, ad esempio costruttori personalizzati, nuovi metodi o gli overload del metodo. Ad esempio, `System.Messaging.MessageQueue` è bloccato e pertanto consente agli utenti di creare code personalizzate che per impostazione predefinita un percorso della coda specifica o per aggiungere metodi personalizzati che consentono di semplificare l'API per scenari specifici.  
  
 Le classi sono sealed o non sealed per impostazione predefinita nei linguaggi di programmazione più, e questo è anche l'impostazione predefinita consigliata per la maggior parte delle classi nel Framework. L'estendibilità ottenibili da tipi non sealed è molto apprezzato dagli utenti di framework e molto conveniente fornire a causa dei costi relativamente basso di test associati ai tipi non sealed.  
  
 *Parti protette da copyright © 2005, 2009 Microsoft Corporation. Tutti i diritti riservati.*  
  
 *Ristampato con l'autorizzazione di Pearson Education, Inc. da [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2a edizione](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) di Krzysztof Cwalina and Brad Abrams, pubblicato il 22 ottobre 2008 da Addison-Wesley Professional nella collana Microsoft Windows Development Series.*  
  
## <a name="see-also"></a>Vedere anche

- [Linee guida per la progettazione di Framework](../../../docs/standard/design-guidelines/index.md)  
- [Progettazione finalizzata all'estensibilità](../../../docs/standard/design-guidelines/designing-for-extensibility.md)  
- [Sealing](../../../docs/standard/design-guidelines/sealing.md)
