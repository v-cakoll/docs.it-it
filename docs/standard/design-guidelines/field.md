---
title: Progettazione di campi
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- fields, design guidelines
- read-only fields
- member design guidelines, fields
ms.assetid: 7cb4b0f3-7a10-4c93-b84d-733f7134fcf8
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2d47934c3fed17f75a97ef5da0397c6ceba53d68
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33571117"
---
# <a name="field-design"></a>Progettazione di campi
Il principio di incapsulamento è uno delle nozioni fondamentali nella progettazione orientata agli oggetti. Questo principio indica che i dati archiviati all'interno di un oggetto devono essere accessibili solo a tale oggetto.  
  
 Un modo utile per interpretare il principio è significa che un tipo deve essere progettato in modo che le modifiche apportate ai campi di quel tipo (nome o il tipo di modifica) possono essere eseguite senza interrompere il codice diverso per i membri del tipo. Questa interpretazione immediatamente implica che tutti i campi devono essere privati.  
  
 Microsoft esclude statici e costanti campi di sola lettura da questa limitazione strict, poiché tali campi, quasi per definizione, non deve modificare.  
  
 **X DO NOT** forniscono i campi di istanza pubblici sono protetti.  
  
 È necessario fornire le proprietà per l'accesso ai campi anziché rendendoli pubblico o protetto.  
  
 **✓ DO** utilizzare i campi costanti per le costanti che non verranno mai modificato.  
  
 Il compilatore esegue il burn-i valori dei campi const direttamente nella chiamata di codice. Pertanto, valori const non possono essere modificati senza il rischio di danneggiare la compatibilità.  
  
 **✓ DO** utilizzare statici pubblici `readonly` campi per le istanze di oggetto predefinito.  
  
 Se sono presenti istanze predefinite del tipo, dichiararli come public campi statici di sola lettura del tipo stesso.  
  
 **X DO NOT** assegna le istanze di tipi modificabili per `readonly` campi.  
  
 Un tipo modificabile è un tipo con le istanze che possono essere modificate dopo la creazione di istanze. Ad esempio, matrici, la maggior parte delle raccolte e i flussi sono tipi modificabili, ma <xref:System.Int32?displayProperty=nameWithType>, <xref:System.Uri?displayProperty=nameWithType>, e <xref:System.String?displayProperty=nameWithType> sono tutti non modificabile. Il modificatore di sola lettura su un campo di tipo riferimento impedisce l'istanza archiviati nel campo venga sostituito, ma non impedisce che i dati del campo istanza vengano modificati chiamando i membri di modifica dell'istanza.  
  
 *Parti © 2005, 2009 Microsoft Corporation. Tutti i diritti riservati.*  
  
 *State ristampate dall'autorizzazione di Pearson Education, Inc. da [linee guida: convenzioni, idiomi e modelli per le librerie .NET di riutilizzabile, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina e Brad Abrams, pubblicato il 22 ottobre 2008 di Addison-Wesley Professional come parte della serie di sviluppo di Microsoft Windows.*  
  
## <a name="see-also"></a>Vedere anche  
 [Linee guida di progettazione dei membri](../../../docs/standard/design-guidelines/member.md)  
 [Linee guida per la progettazione di Framework](../../../docs/standard/design-guidelines/index.md)
