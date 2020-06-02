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
ms.openlocfilehash: 406c15b6ce42b637ed1bbb61761d05e040995579
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "84280244"
---
# <a name="designing-for-extensibility"></a>Progettazione finalizzata all'estensibilità
Un aspetto importante della progettazione di un Framework è garantire che l'estendibilità del Framework sia stata considerata attentamente. A questo scopo è necessario comprendere i costi e i vantaggi associati a vari meccanismi di estendibilità. Questo capitolo aiuta a decidere quale meccanismo di estendibilità, ovvero sottoclassi, eventi, membri virtuali, callback e così via, è in grado di soddisfare al meglio i requisiti del Framework.  
  
 Esistono diversi modi per consentire l'estendibilità nei Framework. Variano da meno potente ma meno costoso a molto potente ma costoso. Per qualsiasi requisito di estendibilità, è necessario scegliere il meccanismo di estendibilità meno costosa che soddisfi i requisiti. Tenere presente che in genere è possibile aggiungere ulteriore estendibilità in un secondo momento, ma non è mai possibile eliminarla senza introdurre modifiche di rilievo.  
  
## <a name="in-this-section"></a>Contenuto della sezione  
 [Classi non sealed](unsealed-classes.md)  
 [Membri protetti](protected-members.md)  
 [Eventi e callback](events-and-callbacks.md)  
 [Membri virtuali](virtual-members.md)  
 [Astrazioni (tipi e interfacce astratte)](abstractions-abstract-types-and-interfaces.md)  
 [Classi base per l'implementazione di astrazioni](base-classes-for-implementing-abstractions.md)  
 [sealed](sealing.md)  
 *Parti © 2005, 2009 Microsoft Corporation. Tutti i diritti riservati.*  
  
 *Ristampato con l'autorizzazione di Pearson Education, Inc. da [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2a edizione](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) di Krzysztof Cwalina and Brad Abrams, pubblicato il 22 ottobre 2008 da Addison-Wesley Professional nella collana Microsoft Windows Development Series.*  
  
## <a name="see-also"></a>Vedere anche

- [Linee guida per la progettazione di Framework](index.md)
