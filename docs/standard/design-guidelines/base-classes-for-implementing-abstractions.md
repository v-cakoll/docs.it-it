---
title: Classi base per l'implementazione di astrazioni
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- abstractions [.NET Framework]
- base classes, abstractions
ms.assetid: 37a2d9a4-9721-482a-a40f-eee2c1d97875
ms.openlocfilehash: 6af63373b7cbb571265f14ac36028953525fcc7f
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "84280569"
---
# <a name="base-classes-for-implementing-abstractions"></a>Classi base per l'implementazione di astrazioni
In modo rigoroso, una classe diventa una classe base quando viene derivata un'altra classe. Ai fini di questa sezione, tuttavia, una classe di base è una classe progettata principalmente per fornire un'astrazione comune o per consentire ad altre classi di riutilizzare un'implementazione predefinita tramite l'ereditarietà. Le classi di base in genere si trovano al centro delle gerarchie di ereditarietà, tra un'astrazione alla radice di una gerarchia e diverse implementazioni personalizzate nella parte inferiore.

 Vengono usati come helper di implementazione per l'implementazione di astrazioni. Ad esempio, una delle astrazioni del Framework per le raccolte ordinate di elementi è l' <xref:System.Collections.Generic.IList%601> interfaccia. <xref:System.Collections.Generic.IList%601>L'implementazione di non è semplice e pertanto il Framework fornisce diverse classi di base, ad esempio <xref:System.Collections.ObjectModel.Collection%601> e <xref:System.Collections.ObjectModel.KeyedCollection%602> , che funge da helper per l'implementazione di raccolte personalizzate.

 Generalmente, le classi base non sono adatte per essere utilizzate come astrazioni, perché tendono a contenere una quantità eccessiva di implementazione. Ad esempio, la `Collection<T>` classe base contiene una grande quantità di implementazione correlata al fatto che implementa l'interfaccia non generica `IList` (per integrarsi meglio con le raccolte non generiche) e il fatto che si tratta di una raccolta di elementi archiviati in memoria in uno dei relativi campi.

 Come descritto in precedenza, le classi di base possono fornire una guida inestimabile per gli utenti che devono implementare astrazioni, ma possono rappresentare una responsabilità significativa. Aggiungono superficie di attacco e aumentano la profondità delle gerarchie di ereditarietà e quindi complicano concettualmente il Framework. Pertanto, le classi di base devono essere utilizzate solo se forniscono un valore significativo agli utenti del Framework. Devono essere evitate se forniscono valore solo agli implementatori del Framework, nel qual caso la delega a un'implementazione interna anziché l'ereditarietà da una classe base deve essere considerata in modo sicuro.

 ✔️ CONSIGLIABILE rendere le classi base astratte anche se non contengono membri astratti. Questo consente di comunicare chiaramente agli utenti che la classe è progettata esclusivamente per essere ereditata da.

 ✔️ CONSIGLIABILE inserire le classi di base in uno spazio dei nomi separato dai tipi di scenario principali. Per definizione, le classi base sono destinate a scenari di estendibilità avanzati e pertanto non sono interessanti per la maggior parte degli utenti.

 ❌EVITARE di denominare le classi di base con un suffisso di base se la classe è destinata all'uso in API pubbliche.

 *Parti © 2005, 2009 Microsoft Corporation. Tutti i diritti riservati.*

 *Ristampato con l'autorizzazione di Pearson Education, Inc. da [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2a edizione](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) di Krzysztof Cwalina and Brad Abrams, pubblicato il 22 ottobre 2008 da Addison-Wesley Professional nella collana Microsoft Windows Development Series.*

## <a name="see-also"></a>Vedere anche

- [Linee guida per la progettazione di Framework](index.md)
- [Progettazione finalizzata all'estensibilità](designing-for-extensibility.md)
