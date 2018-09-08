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
ms.openlocfilehash: 65c54fe9a076a219c61280a98c390b16f56b5015
ms.sourcegitcommit: 64f4baed249341e5bf64d1385bf48e3f2e1a0211
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2018
ms.locfileid: "44127852"
---
# <a name="field-design"></a>Progettazione di campi
Il principio di incapsulamento è uno dei concetti più importanti nella progettazione orientata agli oggetti. Questo principio specifica che i dati archiviati all'interno di un oggetto devono essere accessibili solo a tale oggetto.  
  
 Un modo utile per interpretare il principio è dire che un tipo deve essere progettato in modo che le modifiche apportate ai campi di quel tipo (modifiche di nome o tipo) possono essere eseguite senza causare interruzioni nel codice diverso per i membri del tipo. Questa interpretazione immediatamente significa che tutti i campi devono essere privati.  
  
 Microsoft esclude statici e costanti campi di sola lettura da questa limitazione strict, in quanto tali campi, quasi per definizione, non sono mai richiesto di modificare.  
  
 **X DO NOT** forniscono i campi di istanza pubblici sono protetti.  
  
 È necessario fornire le proprietà per l'accesso ai campi anziché rendendoli pubblico o protetto.  
  
 **✓ DO** utilizzare i campi costanti per le costanti che non verranno mai modificato.  
  
 Il compilatore esegue il burn-i valori dei campi const direttamente nella chiamata di codice. Pertanto, valori const non possono mai essere modificati senza il rischio di compromettere la compatibilità.  
  
 **✓ DO** utilizzare statici pubblici `readonly` campi per le istanze di oggetto predefinito.  
  
 Se sono presenti istanze predefinite del tipo, dichiararli come public campi statici di sola lettura del tipo stesso.  
  
 **X DO NOT** assegna le istanze di tipi modificabili per `readonly` campi.  
  
 Un tipo modificabile è un tipo con istanze che possono essere modificate dopo la creazione di istanze. Ad esempio, matrici, la maggior parte delle raccolte e i flussi sono tipi modificabili, ma <xref:System.Int32?displayProperty=nameWithType>, <xref:System.Uri?displayProperty=nameWithType>, e <xref:System.String?displayProperty=nameWithType> sono tutti modificabili. Il modificatore di sola lettura su un campo di tipo riferimento impedisce l'istanza archiviato nel campo venga sostituito, ma non impedisce che i dati dell'istanza del campo vengano modificati chiamando i membri di modifica dell'istanza.  
  
 *Parti protette da copyright © 2005, 2009 Microsoft Corporation. Tutti i diritti riservati.*  
  
 *Ristampato con l'autorizzazione di Pearson Education, Inc. da [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2a edizione](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) di Krzysztof Cwalina and Brad Abrams, pubblicato il 22 ottobre 2008 da Addison-Wesley Professional nella collana Microsoft Windows Development Series.*  
  
## <a name="see-also"></a>Vedere anche

- [Linee guida di progettazione dei membri](../../../docs/standard/design-guidelines/member.md)  
- [Linee guida per la progettazione di Framework](../../../docs/standard/design-guidelines/index.md)
