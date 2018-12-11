---
title: Cursore1
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- attributes [.NET Framework], about
- class library design guidelines [.NET Framework], attributes
ms.assetid: ee0038ef-b247-4747-a650-3c5c5cd58d8b
author: KrzysztofCwalina
ms.openlocfilehash: 7ab499d5a9c8388e9081a07921d3e444c0cdd879
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/10/2018
ms.locfileid: "53131430"
---
# <a name="attributes"></a>Attributi
<xref:System.Attribute?displayProperty=nameWithType> una classe di base consente di definire attributi personalizzati.  
  
 Gli attributi sono annotazioni che possono essere aggiunti a elementi di programmazione, ad esempio assembly, tipi, membri e parametri. Essi vengono archiviate nei metadati dell'assembly ed è accessibile in fase di esecuzione usando le API di reflection. Ad esempio, il Framework definisce il <xref:System.ObsoleteAttribute>, che può essere applicato a un tipo o membro per indicare che il tipo o membro è stato deprecato.  
  
 Gli attributi possono avere una o più proprietà che contengono dati aggiuntivi correlati all'attributo. Ad esempio, `ObsoleteAttribute` potrebbe contenere informazioni aggiuntive relative alla versione in cui un tipo o membro è stato deprecato e la descrizione delle nuove API sostituendo l'API obsoleta.  
  
 Alcune proprietà di un attributo deve essere specificato quando è applicato l'attributo. Queste vengono denominate le proprietà obbligatorie o gli argomenti obbligatori, in quanto vengono rappresentati come parametri posizionali del costruttore. Ad esempio, il <xref:System.Diagnostics.ConditionalAttribute.ConditionString%2A> proprietà del <xref:System.Diagnostics.ConditionalAttribute> questa proprietà è obbligatoria.  
  
 Le proprietà che non hanno necessariamente specificare quando viene applicato l'attributo vengono chiamate proprietà facoltative (o gli argomenti facoltativi). Sono rappresentate da proprietà impostabili. I compilatori forniscono una sintassi speciale per impostare queste proprietà quando viene applicato un attributo. Ad esempio, il <xref:System.AttributeUsageAttribute.Inherited%2A?displayProperty=nameWithType> proprietà rappresenta un argomento facoltativo.  
  
 **✓ DO** denominare le classi di attributo personalizzato con il suffisso "Attributo".  
  
 **✓ DO** applica il <xref:System.AttributeUsageAttribute> per gli attributi personalizzati.  
  
 **✓ DO** forniscono le proprietà impostabili per gli argomenti facoltativi.  
  
 **✓ DO** forniscono proprietà solo get per gli argomenti obbligatori.  
  
 **✓ DO** forniscono i parametri del costruttore per inizializzare le proprietà corrispondenti per gli argomenti obbligatori. Ogni parametro deve avere lo stesso nome (anche se con maiuscole e minuscole diverse) come la proprietà corrispondente.  
  
 **X AVOID** fornendo i parametri del costruttore per inizializzare le proprietà corrispondenti per gli argomenti facoltativi.  
  
 In altre parole, non includono proprietà che possono essere impostate con un costruttore e un setter. Questa linea guida rende molto esplicite quali gli argomenti sono facoltativi e sono necessari che consenta di evitare la due modi di ottenere la stessa cosa.  
  
 **X AVOID** l'overload di costruttori di attributo personalizzato.  
  
 Con un solo costruttore chiaramente comunica all'utente cui gli argomenti sono obbligatori e facoltativi.  
  
 **✓ DO** proteggere le classi di attributo personalizzato, se possibile. In questo modo la ricerca per l'attributo più velocemente.  
  
 *Parti protette da copyright © 2005, 2009 Microsoft Corporation. Tutti i diritti riservati.*  
  
 *Ristampato con l'autorizzazione di Pearson Education, Inc. dal [linee guida di progettazione di Framework: Convenzioni, linguaggi e modelli per le librerie .NET di riutilizzabile, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina e Brad Abrams, pubblicato il 22 ottobre 2008 da Addison-Wesley Professional come parte della serie di sviluppo di Microsoft Windows.*  
  
## <a name="see-also"></a>Vedere anche

- [Linee guida per la progettazione di Framework](../../../docs/standard/design-guidelines/index.md)  
- [Linee guida per l'uso](../../../docs/standard/design-guidelines/usage-guidelines.md)
