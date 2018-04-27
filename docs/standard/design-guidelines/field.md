---
title: Progettazione di campi
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology: dotnet-standard
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- fields, design guidelines
- read-only fields
- member design guidelines, fields
ms.assetid: 7cb4b0f3-7a10-4c93-b84d-733f7134fcf8
caps.latest.revision: 10
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 102c52a125c3f34dc027d01eecd24f13613e20c6
ms.sourcegitcommit: 2e8acae16ae802f2d6d04e3ce0a6dbf04e476513
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2018
---
# <a name="field-design"></a>Progettazione di campi
Il principio di incapsulamento è uno delle nozioni fondamentali nella progettazione orientata agli oggetti. Questo principio indica che i dati archiviati all'interno di un oggetto devono essere accessibili solo a tale oggetto.  
  
 Un modo utile per interpretare il principio è significa che un tipo deve essere progettato in modo che le modifiche apportate ai campi di quel tipo (nome o il tipo di modifica) possono essere eseguite senza interrompere il codice diverso per i membri del tipo. Questa interpretazione immediatamente implica che tutti i campi devono essere privati.  
  
 Microsoft esclude statici e costanti campi di sola lettura da questa limitazione strict, poiché tali campi, quasi per definizione, non deve modificare.  
  
 **X non** forniscono i campi di istanza pubblici sono protetti.  
  
 È necessario fornire le proprietà per l'accesso ai campi anziché rendendoli pubblico o protetto.  
  
 **✓ SI** utilizzare i campi costanti per le costanti che non verranno mai modificato.  
  
 Il compilatore esegue il burn-i valori dei campi const direttamente nella chiamata di codice. Pertanto, valori const non possono essere modificati senza il rischio di danneggiare la compatibilità.  
  
 **✓ SI** utilizzare statici pubblici `readonly` campi per le istanze di oggetto predefinito.  
  
 Se sono presenti istanze predefinite del tipo, dichiararli come public campi statici di sola lettura del tipo stesso.  
  
 **X non** assegna le istanze di tipi modificabili per `readonly` campi.  
  
 Un tipo modificabile è un tipo con le istanze che possono essere modificate dopo la creazione di istanze. Ad esempio, matrici, la maggior parte delle raccolte e i flussi sono tipi modificabili, ma <xref:System.Int32?displayProperty=nameWithType>, <xref:System.Uri?displayProperty=nameWithType>, e <xref:System.String?displayProperty=nameWithType> sono tutti non modificabile. Il modificatore di sola lettura su un campo di tipo riferimento impedisce l'istanza archiviati nel campo venga sostituito, ma non impedisce che i dati del campo istanza vengano modificati chiamando i membri di modifica dell'istanza.  
  
 *Parti © 2005, 2009 Microsoft Corporation. Tutti i diritti riservati.*  
  
 *State ristampate dall'autorizzazione di Pearson Education, Inc. da [linee guida: convenzioni, idiomi e modelli per le librerie .NET di riutilizzabile, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina e Brad Abrams, pubblicato il 22 ottobre 2008 di Addison-Wesley Professional come parte della serie di sviluppo di Microsoft Windows.*  
  
## <a name="see-also"></a>Vedere anche  
 [Linee guida di progettazione dei membri](../../../docs/standard/design-guidelines/member.md)  
 [Linee guida per la progettazione di Framework](../../../docs/standard/design-guidelines/index.md)
