---
title: Attributi
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- attributes [.NET Framework], about
- class library design guidelines [.NET Framework], attributes
ms.assetid: ee0038ef-b247-4747-a650-3c5c5cd58d8b
ms.openlocfilehash: c7bbbda88bd2fddb235b9ae639848e08a452c913
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76741795"
---
# <a name="attributes"></a>Attributi
<xref:System.Attribute?displayProperty=nameWithType> è una classe di base utilizzata per definire attributi personalizzati.

 Gli attributi sono annotazioni che possono essere aggiunte a elementi di programmazione quali assembly, tipi, membri e parametri. Sono archiviati nei metadati dell'assembly ed è possibile accedervi in fase di esecuzione usando le API di Reflection. Il Framework, ad esempio, definisce il <xref:System.ObsoleteAttribute>, che può essere applicato a un tipo o a un membro per indicare che il tipo o il membro è stato deprecato.

 Gli attributi possono avere una o più proprietà che contengono dati aggiuntivi correlati all'attributo. Ad esempio, `ObsoleteAttribute` potrebbe contenere informazioni aggiuntive sulla versione in cui un tipo o un membro è stato deprecato e la descrizione delle nuove API che sostituiscono l'API obsoleta.

 Quando l'attributo viene applicato, è necessario specificare alcune proprietà di un attributo. Queste proprietà sono denominate proprietà obbligatorie o argomenti obbligatori, perché sono rappresentate come parametri del costruttore posizionale. Ad esempio, la proprietà <xref:System.Diagnostics.ConditionalAttribute.ConditionString%2A> del <xref:System.Diagnostics.ConditionalAttribute> è una proprietà obbligatoria.

 Le proprietà che non devono necessariamente essere specificate quando l'attributo viene applicato sono denominate proprietà facoltative (o argomenti facoltativi). Sono rappresentate da proprietà impostabili. I compilatori forniscono una sintassi speciale per impostare queste proprietà quando viene applicato un attributo. Ad esempio, la proprietà <xref:System.AttributeUsageAttribute.Inherited%2A?displayProperty=nameWithType> rappresenta un argomento facoltativo.

 ✔️ denominare le classi di attributi personalizzate con il suffisso "Attribute".

 ✔️ applicare la <xref:System.AttributeUsageAttribute> agli attributi personalizzati.

 ✔️ forniscono proprietà impostabili per gli argomenti facoltativi.

 ✔️ forniscono proprietà solo Get per gli argomenti obbligatori.

 ✔️ forniscono i parametri del costruttore per inizializzare le proprietà corrispondenti agli argomenti obbligatori. Ogni parametro deve avere lo stesso nome (anche se con maiuscole e minuscole diverse) come proprietà corrispondente.

 ❌ evitare di fornire parametri del costruttore per inizializzare proprietà corrispondenti agli argomenti facoltativi.

 In altre parole, non dispongono di proprietà che possono essere impostate con un costruttore e un setter. Questa linea guida rende molto espliciti gli argomenti facoltativi e quelli necessari, evitando di avere due modi per eseguire la stessa operazione.

 ❌ evitare l'overload di costruttori di attributi personalizzati.

 La presenza di un solo costruttore comunica chiaramente all'utente quali argomenti sono obbligatori e quali sono facoltativi.

 ✔️ ESEGUE il sealing delle classi di attributi personalizzate, se possibile. Questa operazione rende più veloce la ricerca dell'attributo.

 *Parti © 2005, 2009 Microsoft Corporation. Tutti i diritti riservati.*

 *Ristampato con l'autorizzazione di Pearson Education, Inc. da [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2a edizione](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) di Krzysztof Cwalina and Brad Abrams, pubblicato il 22 ottobre 2008 da Addison-Wesley Professional nella collana Microsoft Windows Development Series.*

## <a name="see-also"></a>Vedere anche

- [Linee guida per la progettazione di Framework](../../../docs/standard/design-guidelines/index.md)
- [Linee guida per l'uso](../../../docs/standard/design-guidelines/usage-guidelines.md)
