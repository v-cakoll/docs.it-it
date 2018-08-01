---
title: Oggetti Attributes1
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- attributes [.NET Framework], about
- class library design guidelines [.NET Framework], attributes
ms.assetid: ee0038ef-b247-4747-a650-3c5c5cd58d8b
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 493ac709123c67311ba570894fb324ae7148bfae
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33574634"
---
# <a name="attributes"></a>Attributi
<xref:System.Attribute?displayProperty=nameWithType> una classe di base consente di definire attributi personalizzati.  
  
 Gli attributi sono le annotazioni possono essere aggiunti a elementi di programmazione, ad esempio assembly, tipi, membri e parametri. Essi vengono archiviate nei metadati dell'assembly e accessibile in fase di esecuzione usando l'API di reflection. Ad esempio, il Framework definisce il <xref:System.ObsoleteAttribute>, che può essere applicato a un tipo o un membro per indicare che il tipo o membro è stato deprecato.  
  
 Gli attributi possono avere uno o più proprietà che contengono dati aggiuntivi relativi all'attributo. Ad esempio, `ObsoleteAttribute` potrebbe contenere informazioni aggiuntive sulla versione in cui un tipo o membro è stato deprecato e la descrizione delle nuove API sostituendo l'API obsoleta.  
  
 Alcune proprietà di un attributo deve essere specificata quando è applicato l'attributo. Questi sono definiti per le proprietà obbligatorie o gli argomenti obbligatori, poiché vengono rappresentati come parametri posizionali di costruttore. Ad esempio, il <xref:System.Diagnostics.ConditionalAttribute.ConditionString%2A> proprietà del <xref:System.Diagnostics.ConditionalAttribute> è una proprietà obbligatoria.  
  
 Proprietà che non è necessario specificare quando è applicato l'attributo sono dette proprietà facoltative (o gli argomenti facoltativi). Sono rappresentati dalle proprietà impostabili. I compilatori forniscono una sintassi speciale per impostare queste proprietà quando viene applicato un attributo. Ad esempio, il <xref:System.AttributeUsageAttribute.Inherited%2A?displayProperty=nameWithType> proprietà rappresenta un argomento facoltativo.  
  
 **✓ DO** denominare le classi di attributo personalizzato con il suffisso "Attributo".  
  
 **✓ DO** applica il <xref:System.AttributeUsageAttribute> per gli attributi personalizzati.  
  
 **✓ DO** forniscono le proprietà impostabili per gli argomenti facoltativi.  
  
 **✓ DO** forniscono proprietà solo get per gli argomenti obbligatori.  
  
 **✓ DO** forniscono i parametri del costruttore per inizializzare le proprietà corrispondenti per gli argomenti obbligatori. Ogni parametro deve avere lo stesso nome (anche se con maiuscole/minuscole) della proprietà corrispondente.  
  
 **X AVOID** fornendo i parametri del costruttore per inizializzare le proprietà corrispondenti per gli argomenti facoltativi.  
  
 In altre parole, non dispone delle proprietà che è possibile impostare con un costruttore e un setter. Questa linea guida rende molto esplicite gli argomenti sono facoltativi e che sono necessari e si evita due modi per eseguire la stessa operazione.  
  
 **X AVOID** l'overload di costruttori di attributo personalizzato.  
  
 Presenza di un solo costruttore chiaramente comunica all'utente cui gli argomenti sono obbligatori e facoltativi.  
  
 **✓ DO** proteggere le classi di attributo personalizzato, se possibile. In questo modo la ricerca per l'attributo più velocemente.  
  
 *Parti © 2005, 2009 Microsoft Corporation. Tutti i diritti riservati.*  
  
 *State ristampate dall'autorizzazione di Pearson Education, Inc. da [linee guida: convenzioni, idiomi e modelli per le librerie .NET di riutilizzabile, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina e Brad Abrams, pubblicato il 22 ottobre 2008 di Addison-Wesley Professional come parte della serie di sviluppo di Microsoft Windows.*  
  
## <a name="see-also"></a>Vedere anche  
 [Linee guida per la progettazione di Framework](../../../docs/standard/design-guidelines/index.md)  
 [Linee guida per l'uso](../../../docs/standard/design-guidelines/usage-guidelines.md)
