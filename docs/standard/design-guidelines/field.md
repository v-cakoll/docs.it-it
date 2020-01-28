---
title: Progettazione di campi
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- fields, design guidelines
- read-only fields
- member design guidelines, fields
ms.assetid: 7cb4b0f3-7a10-4c93-b84d-733f7134fcf8
ms.openlocfilehash: c00929ca499e39bd4e24d482c9413beb9cccddc1
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76741601"
---
# <a name="field-design"></a>Progettazione di campi
Il principio di incapsulamento è uno dei concetti più importanti della progettazione orientata a oggetti. Questo principio indica che i dati archiviati all'interno di un oggetto devono essere accessibili solo a tale oggetto.

 Un modo utile per interpretare il principio è quello di indicare che un tipo deve essere progettato in modo che sia possibile apportare modifiche ai campi di quel tipo (nome o tipo) senza suddividere il codice per i membri del tipo. Questa interpretazione implica immediatamente che tutti i campi debbano essere privati.

 Si escludono i campi costanti e statici di sola lettura da questa restrizione restrittiva, perché tali campi, quasi per definizione, non sono mai necessari per la modifica.

 ❌ non forniscono campi di istanza pubblici o protetti.

 È necessario specificare le proprietà per l'accesso ai campi, anziché renderle pubbliche o protette.

 ✔️ utilizzano campi costanti per le costanti che non vengono mai modificate.

 Il compilatore brucia i valori dei campi const direttamente nel codice chiamante. Pertanto, i valori const non possono mai essere modificati senza il rischio di interruzioni della compatibilità.

 ✔️ utilizzare i campi `readonly` statici pubblici per le istanze di oggetti predefinite.

 Se sono presenti istanze predefinite del tipo, dichiararle come campi statici di sola lettura pubblici del tipo stesso.

 ❌ non assegnare istanze di tipi modificabili ai campi `readonly`.

 Un tipo modificabile è un tipo con istanze che possono essere modificate dopo la creazione di istanze. Ad esempio, le matrici, la maggior parte delle raccolte e i flussi sono tipi modificabili, ma <xref:System.Int32?displayProperty=nameWithType>, <xref:System.Uri?displayProperty=nameWithType>e <xref:System.String?displayProperty=nameWithType> sono tutti non modificabili. Il modificatore di sola lettura in un campo di tipo riferimento impedisce che l'istanza archiviata nel campo venga sostituita, ma non impedisce la modifica dei dati dell'istanza del campo chiamando membri che modificano l'istanza.

 *Parti © 2005, 2009 Microsoft Corporation. Tutti i diritti riservati.*

 *Ristampato con l'autorizzazione di Pearson Education, Inc. da [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2a edizione](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) di Krzysztof Cwalina and Brad Abrams, pubblicato il 22 ottobre 2008 da Addison-Wesley Professional nella collana Microsoft Windows Development Series.*

## <a name="see-also"></a>Vedere anche

- [Linee guida di progettazione dei membri](../../../docs/standard/design-guidelines/member.md)
- [Linee guida per la progettazione di Framework](../../../docs/standard/design-guidelines/index.md)
