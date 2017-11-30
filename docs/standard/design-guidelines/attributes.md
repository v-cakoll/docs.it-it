---
title: Oggetti Attributes1
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- attributes [.NET Framework], about
- class library design guidelines [.NET Framework], attributes
ms.assetid: ee0038ef-b247-4747-a650-3c5c5cd58d8b
caps.latest.revision: "16"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 86fa2556e6b8fb82e31a7d4753354aa2dff627ff
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="attributes"></a>Attributi
<xref:System.Attribute?displayProperty=nameWithType>è una classe di base utilizzata per definire gli attributi personalizzati.  
  
 Gli attributi sono le annotazioni possono essere aggiunti a elementi di programmazione, ad esempio assembly, tipi, membri e parametri. Essi vengono archiviate nei metadati dell'assembly e accessibile in fase di esecuzione usando l'API di reflection. Ad esempio, il Framework definisce il <xref:System.ObsoleteAttribute>, che può essere applicato a un tipo o un membro per indicare che il tipo o membro è stato deprecato.  
  
 Gli attributi possono avere uno o più proprietà che contengono dati aggiuntivi relativi all'attributo. Ad esempio, `ObsoleteAttribute` potrebbe contenere informazioni aggiuntive sulla versione in cui un tipo o membro è stato deprecato e la descrizione delle nuove API sostituendo l'API obsoleta.  
  
 Alcune proprietà di un attributo deve essere specificata quando è applicato l'attributo. Questi sono definiti per le proprietà obbligatorie o gli argomenti obbligatori, poiché vengono rappresentati come parametri posizionali di costruttore. Ad esempio, il <xref:System.Diagnostics.ConditionalAttribute.ConditionString%2A> proprietà del <xref:System.Diagnostics.ConditionalAttribute> è una proprietà obbligatoria.  
  
 Proprietà che non è necessario specificare quando è applicato l'attributo sono dette proprietà facoltative (o gli argomenti facoltativi). Sono rappresentati dalle proprietà impostabili. I compilatori forniscono una sintassi speciale per impostare queste proprietà quando viene applicato un attributo. Ad esempio, il <xref:System.AttributeUsageAttribute.Inherited%2A?displayProperty=nameWithType> proprietà rappresenta un argomento facoltativo.  
  
 **✓ SI** denominare le classi di attributo personalizzato con il suffisso "Attributo".  
  
 **✓ SI** applicare il <xref:System.AttributeUsageAttribute> per gli attributi personalizzati.  
  
 **✓ SI** fornire proprietà impostabili per gli argomenti facoltativi.  
  
 **✓ SI** forniscono proprietà solo get per gli argomenti obbligatori.  
  
 **✓ SI** forniscono i parametri del costruttore per inizializzare le proprietà corrispondenti per gli argomenti obbligatori. Ogni parametro deve avere lo stesso nome (anche se con maiuscole/minuscole) della proprietà corrispondente.  
  
 **X evitare** fornendo i parametri del costruttore per inizializzare le proprietà corrispondenti per gli argomenti facoltativi.  
  
 In altre parole, non dispone delle proprietà che è possibile impostare con un costruttore e un setter. Questa linea guida rende molto esplicite gli argomenti sono facoltativi e che sono necessari e si evita due modi per eseguire la stessa operazione.  
  
 **X evitare** l'overload di costruttori di attributo personalizzato.  
  
 Presenza di un solo costruttore chiaramente comunica all'utente cui gli argomenti sono obbligatori e facoltativi.  
  
 **✓ SI** bloccare le classi di attributo personalizzato, se possibile. In questo modo la ricerca per l'attributo più velocemente.  
  
 *Parti © 2005, 2009 Microsoft Corporation. Tutti i diritti riservati.*  
  
 *State ristampate dall'autorizzazione di Pearson Education, Inc. da [linee guida: convenzioni, idiomi e modelli per le librerie .NET di riutilizzabile, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina e Brad Abrams, pubblicato il 22 ottobre 2008 di Addison-Wesley Professional come parte della serie di sviluppo di Microsoft Windows.*  
  
## <a name="see-also"></a>Vedere anche  
 [Linee guida per la progettazione di Framework](../../../docs/standard/design-guidelines/index.md)  
 [Linee guida di utilizzo](../../../docs/standard/design-guidelines/usage-guidelines.md)
