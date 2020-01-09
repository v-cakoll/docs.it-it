---
title: Progettazione finalizzata all'estensibilità
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- extending class libraries
- extensibility with class libraries in .NET Framework
- class library design guidelines [.NET Framework], extensibility
- class library extensibility [.NET Framework]
ms.assetid: 1cdb8740-871a-456c-9bd9-db96ca8d79b3
ms.openlocfilehash: cd5db2d1e299df1b3d0f706ebc507e6855b72505
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75709465"
---
# <a name="designing-for-extensibility"></a>Progettazione finalizzata all'estensibilità
Un aspetto importante della progettazione di un Framework è garantire che l'estendibilità del Framework sia stata considerata attentamente. A questo scopo è necessario comprendere i costi e i vantaggi associati a vari meccanismi di estendibilità. Questo capitolo aiuta a decidere quale meccanismo di estendibilità, ovvero sottoclassi, eventi, membri virtuali, callback e così via, è in grado di soddisfare al meglio i requisiti del Framework.  
  
 Esistono diversi modi per consentire l'estendibilità nei Framework. Variano da meno potente ma meno costoso a molto potente ma costoso. Per qualsiasi requisito di estendibilità, è necessario scegliere il meccanismo di estendibilità meno costosa che soddisfi i requisiti. Tenere presente che in genere è possibile aggiungere ulteriore estendibilità in un secondo momento, ma non è mai possibile eliminarla senza introdurre modifiche di rilievo.  
  
## <a name="in-this-section"></a>In questa sezione  
 [Classi non sealed](../../../docs/standard/design-guidelines/unsealed-classes.md)  
 [Membri protetti](../../../docs/standard/design-guidelines/protected-members.md)  
 [Eventi e callback](../../../docs/standard/design-guidelines/events-and-callbacks.md)  
 [Membri virtuali](../../../docs/standard/design-guidelines/virtual-members.md)  
 [Astrazioni (interfacce e tipi astratti)](../../../docs/standard/design-guidelines/abstractions-abstract-types-and-interfaces.md)  
 [Classi base per l'implementazione di astrazioni](../../../docs/standard/design-guidelines/base-classes-for-implementing-abstractions.md)  
 [Sealing](../../../docs/standard/design-guidelines/sealing.md)  
 *Parti © 2005, 2009 Microsoft Corporation. Tutti i diritti riservati.*  
  
 *Ristampato con l'autorizzazione di Pearson Education, Inc. da [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2a edizione](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) di Krzysztof Cwalina and Brad Abrams, pubblicato il 22 ottobre 2008 da Addison-Wesley Professional nella collana Microsoft Windows Development Series.*  
  
## <a name="see-also"></a>Vedere anche

- [Linee guida per la progettazione di Framework](../../../docs/standard/design-guidelines/index.md)
