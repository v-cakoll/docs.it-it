---
title: Progettazione finalizzata all'estensibilità
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- extending class libraries
- extensibility with class libraries in .NET Framework
- class library design guidelines [.NET Framework], extensibility
- class library extensibility [.NET Framework]
ms.assetid: 1cdb8740-871a-456c-9bd9-db96ca8d79b3
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9c1690d0cdf1f57eaf0a794d6e71babfa4fa6425
ms.sourcegitcommit: ad99773e5e45068ce03b99518008397e1299e0d1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/22/2018
ms.locfileid: "46697529"
---
# <a name="designing-for-extensibility"></a>Progettazione finalizzata all'estensibilità
Un aspetto importante della progettazione di un framework è assicurare che l'estendibilità del framework è stato considerato con attenzione. È necessario comprendere i costi e vantaggi associati vari meccanismi di estendibilità. In questo capitolo contribuisce di stabilire quale dei meccanismi di estendibilità: creazione di una sottoclasse, eventi, i membri virtuali, callback e così via, possano soddisfare i requisiti del framework.  
  
 Esistono diversi modi per consentire di estendibilità nel Framework. Sono compresi tra meno potenti, ma meno onerosi e molto potenti ma dispendioso. Per qualsiasi requisito di estendibilità specifico, è consigliabile scegliere il meccanismo di estendibilità meno costoso che soddisfi i requisiti. Tenere presente che in genere è possibile aggiungere maggiore estendibilità in un secondo momento, ma è bene non creare immediatamente senza introdurre modifiche di rilievo.  
  
## <a name="in-this-section"></a>In questa sezione  
 [Classi non sealed](../../../docs/standard/design-guidelines/unsealed-classes.md)  
 [Membri protetti](../../../docs/standard/design-guidelines/protected-members.md)  
 [Eventi e callback](../../../docs/standard/design-guidelines/events-and-callbacks.md)  
 [Membri virtuali](../../../docs/standard/design-guidelines/virtual-members.md)  
 [Astrazioni (interfacce e tipi astratti)](../../../docs/standard/design-guidelines/abstractions-abstract-types-and-interfaces.md)  
 [Classi base per l'implementazione di astrazioni](../../../docs/standard/design-guidelines/base-classes-for-implementing-abstractions.md)  
 [Sealing](../../../docs/standard/design-guidelines/sealing.md)  
 *Parti protette da copyright © 2005, 2009 Microsoft Corporation. Tutti i diritti riservati.*  
  
 *Ristampato con l'autorizzazione di Pearson Education, Inc. da [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2a edizione](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) di Krzysztof Cwalina and Brad Abrams, pubblicato il 22 ottobre 2008 da Addison-Wesley Professional nella collana Microsoft Windows Development Series.*  
  
## <a name="see-also"></a>Vedere anche

- [Linee guida per la progettazione di Framework](../../../docs/standard/design-guidelines/index.md)
