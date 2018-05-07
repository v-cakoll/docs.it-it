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
ms.openlocfilehash: 68419fe293dd25936aa3c1e3def10bbe8852e175
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="designing-for-extensibility"></a>Progettazione finalizzata all'estensibilità
Un aspetto importante della progettazione di un framework consiste nel garantire che l'estendibilità del framework è stato considerato con attenzione. È necessario comprendere i costi e i vantaggi associati a vari meccanismi di estendibilità. Questo capitolo consente di decidere quale dei meccanismi di estendibilità: creazione di una sottoclasse, eventi, i membri virtuali, i callback e così via, possano soddisfare i requisiti del framework di.  
  
 Esistono diversi modi per consentire l'estensibilità in Framework. Vanno da meno potenti ma meno costose da molto potenti ma costosa. Per qualsiasi requisito di estendibilità specifico, è necessario scegliere il meccanismo di estendibilità meno costoso che soddisfi i requisiti. Tenere presente che è in genere, è possibile aggiungere ulteriori estendibilità in un secondo momento, ma è mai possibile trasferirli immediatamente senza introdurre modifiche di rilievo.  
  
## <a name="in-this-section"></a>In questa sezione  
 [Classi non sealed](../../../docs/standard/design-guidelines/unsealed-classes.md)  
 [Membri protetti](../../../docs/standard/design-guidelines/protected-members.md)  
 [Eventi e callback](../../../docs/standard/design-guidelines/events-and-callbacks.md)  
 [Membri virtuali](../../../docs/standard/design-guidelines/virtual-members.md)  
 [Astrazioni (interfacce e tipi astratti)](../../../docs/standard/design-guidelines/abstractions-abstract-types-and-interfaces.md)  
 [Classi base per l'implementazione di astrazioni](../../../docs/standard/design-guidelines/base-classes-for-implementing-abstractions.md)  
 [Sealing](../../../docs/standard/design-guidelines/sealing.md)  
 *Parti © 2005, 2009 Microsoft Corporation. Tutti i diritti riservati.*  
  
 *State ristampate dall'autorizzazione di Pearson Education, Inc. da [linee guida: convenzioni, idiomi e modelli per le librerie .NET di riutilizzabile, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina e Brad Abrams, pubblicato il 22 ottobre 2008 di Addison-Wesley Professional come parte della serie di sviluppo di Microsoft Windows.*  
  
## <a name="see-also"></a>Vedere anche  
 [Linee guida per la progettazione di Framework](../../../docs/standard/design-guidelines/index.md)
