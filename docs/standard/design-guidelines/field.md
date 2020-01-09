---
title: Progettazione di campi
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- fields, design guidelines
- read-only fields
- member design guidelines, fields
ms.assetid: 7cb4b0f3-7a10-4c93-b84d-733f7134fcf8
ms.openlocfilehash: d39c9b95d759902d6d523b028f3db8b8da954336
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75709348"
---
# <a name="field-design"></a>Progettazione di campi
Il principio di incapsulamento è uno dei concetti più importanti della progettazione orientata a oggetti. Questo principio indica che i dati archiviati all'interno di un oggetto devono essere accessibili solo a tale oggetto.  
  
 Un modo utile per interpretare il principio è quello di indicare che un tipo deve essere progettato in modo che sia possibile apportare modifiche ai campi di quel tipo (nome o tipo) senza suddividere il codice per i membri del tipo. Questa interpretazione implica immediatamente che tutti i campi debbano essere privati.  
  
 Si escludono i campi costanti e statici di sola lettura da questa restrizione restrittiva, perché tali campi, quasi per definizione, non sono mai necessari per la modifica.  
  
 **X DO NOT** forniscono i campi di istanza pubblici sono protetti.  
  
 È necessario specificare le proprietà per l'accesso ai campi, anziché renderle pubbliche o protette.  
  
 **✓ DO** utilizzare i campi costanti per le costanti che non verranno mai modificato.  
  
 Il compilatore brucia i valori dei campi const direttamente nel codice chiamante. Pertanto, i valori const non possono mai essere modificati senza il rischio di interruzioni della compatibilità.  
  
 **✓ DO** utilizzare statici pubblici `readonly` campi per le istanze di oggetto predefinito.  
  
 Se sono presenti istanze predefinite del tipo, dichiararle come campi statici di sola lettura pubblici del tipo stesso.  
  
 **X DO NOT** assegna le istanze di tipi modificabili per `readonly` campi.  
  
 Un tipo modificabile è un tipo con istanze che possono essere modificate dopo la creazione di istanze. Ad esempio, le matrici, la maggior parte delle raccolte e i flussi sono tipi modificabili, ma <xref:System.Int32?displayProperty=nameWithType>, <xref:System.Uri?displayProperty=nameWithType>e <xref:System.String?displayProperty=nameWithType> sono tutti non modificabili. Il modificatore di sola lettura in un campo di tipo riferimento impedisce che l'istanza archiviata nel campo venga sostituita, ma non impedisce la modifica dei dati dell'istanza del campo chiamando membri che modificano l'istanza.  
  
 *Parti © 2005, 2009 Microsoft Corporation. Tutti i diritti riservati.*  
  
 *Ristampato con l'autorizzazione di Pearson Education, Inc. da [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2a edizione](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) di Krzysztof Cwalina and Brad Abrams, pubblicato il 22 ottobre 2008 da Addison-Wesley Professional nella collana Microsoft Windows Development Series.*  
  
## <a name="see-also"></a>Vedere anche

- [Linee guida di progettazione dei membri](../../../docs/standard/design-guidelines/member.md)
- [Linee guida per la progettazione di Framework](../../../docs/standard/design-guidelines/index.md)
