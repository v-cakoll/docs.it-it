---
title: Progettazione di struct
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology: dotnet-standard
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- class library design guidelines [.NET Framework], structures
- deallocating structures
- allocating structures
- value types, structures
- structure design
- type design guidelines, structures
- structures [.NET Framework], design guidelines
ms.assetid: 1f48b2d8-608c-4be6-9ba4-d8f203ed9f9f
caps.latest.revision: 12
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: dfa32112a2eb85a93cdd1e7a72d4411a3b197a1a
ms.sourcegitcommit: 2e8acae16ae802f2d6d04e3ce0a6dbf04e476513
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2018
---
# <a name="struct-design"></a>Progettazione di struct
Il tipo di valore generici è più noto anche come una struttura, la parola chiave c#. In questa sezione vengono fornite linee guida per la progettazione struttura generale.  
  
 **X non** fornisce un costruttore predefinito per uno struct.  
  
 Seguendo questa linea guida gli matrici di strutture possono essere creati senza dover eseguire il costruttore su ogni elemento della matrice. Si noti che in c# non consente strutture possono disporre di costruttori predefiniti.  
  
 **X non** definire i tipi di valore modificabile.  
  
 Tipi di valore modificabile hanno vari problemi. Ad esempio, quando una proprietà get restituisce un tipo di valore, il chiamante riceve una copia. Poiché la copia viene creata in modo implicito, gli sviluppatori potrebbero non essere consapevoli che sono la mutazione di copia e non il valore originale. Inoltre, alcuni linguaggi (linguaggi dinamici, in particolare) verificarsi dei problemi con i tipi di valore modificabile perché anche le variabili locali, quando viene dereferenziato, provocare una copia da eseguire.  
  
 **✓ SI** garantire che in uno stato in cui tutti i dati dell'istanza è impostato su zero, false o null (se necessario) è valido.  
  
 Ciò impedisce la creazione accidentale di istanze non valide quando viene creata una matrice di strutture.  
  
 **✓ SI** implementare <xref:System.IEquatable%601> sui tipi di valore.  
  
 Il <xref:System.Object.Equals%2A?displayProperty=nameWithType> metodo nei tipi di valore determina la conversione boxing e l'implementazione predefinita non è molto efficiente, perché usa la reflection. <xref:System.IEquatable%601.Equals%2A> può avere prestazioni migliori e può essere implementato in modo che non causa la conversione boxing.  
  
 **X non** estendere in modo esplicito <xref:System.ValueType>. In effetti, la maggior parte dei linguaggi evitare questo problema.  
  
 In generale, le strutture possono rivelarsi molto utile, ma devono essere utilizzate solo per i valori di piccole dimensioni, single, non modificabili che non essere boxed frequentemente.  
  
 *Parti © 2005, 2009 Microsoft Corporation. Tutti i diritti riservati.*  
  
 *State ristampate dall'autorizzazione di Pearson Education, Inc. da [linee guida: convenzioni, idiomi e modelli per le librerie .NET di riutilizzabile, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina e Brad Abrams, pubblicato il 22 ottobre 2008 di Addison-Wesley Professional come parte della serie di sviluppo di Microsoft Windows.*  
  
## <a name="see-also"></a>Vedere anche  
 [Linee guida per la progettazione di tipi](../../../docs/standard/design-guidelines/type.md)  
 [Linee guida per la progettazione di Framework](../../../docs/standard/design-guidelines/index.md)  
 [Scelta tra classi e struct](../../../docs/standard/design-guidelines/choosing-between-class-and-struct.md)
