---
title: Progettazione di campi
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- fields, design guidelines
- read-only fields
- member design guidelines, fields
ms.assetid: 7cb4b0f3-7a10-4c93-b84d-733f7134fcf8
ms.openlocfilehash: 3a5ae985ab161899fbb5e96f9b0ef0cfa90b957c
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "84289746"
---
# <a name="field-design"></a>Progettazione di campi
Il principio di incapsulamento è uno dei concetti più importanti della progettazione orientata a oggetti. Questo principio indica che i dati archiviati all'interno di un oggetto devono essere accessibili solo a tale oggetto.

 Un modo utile per interpretare il principio è quello di indicare che un tipo deve essere progettato in modo che sia possibile apportare modifiche ai campi di quel tipo (nome o tipo) senza suddividere il codice per i membri del tipo. Questa interpretazione implica immediatamente che tutti i campi debbano essere privati.

 Si escludono i campi costanti e statici di sola lettura da questa restrizione restrittiva, perché tali campi, quasi per definizione, non sono mai necessari per la modifica.

 ❌Non specificare campi di istanza pubblici o protetti.

 È necessario specificare le proprietà per l'accesso ai campi, anziché renderle pubbliche o protette.

 ✔️ utilizzano campi costanti per le costanti che non vengono mai modificate.

 Il compilatore brucia i valori dei campi const direttamente nel codice chiamante. Pertanto, i valori const non possono mai essere modificati senza il rischio di interruzioni della compatibilità.

 ✔️ usare campi statici pubblici `readonly` per le istanze di oggetti predefinite.

 Se sono presenti istanze predefinite del tipo, dichiararle come campi statici di sola lettura pubblici del tipo stesso.

 ❌NON assegnare istanze di tipi modificabili ai `readonly` campi.

 Un tipo modificabile è un tipo con istanze che possono essere modificate dopo la creazione di istanze. Ad esempio, le matrici, la maggior parte delle raccolte e i flussi sono tipi modificabili, ma <xref:System.Int32?displayProperty=nameWithType> , <xref:System.Uri?displayProperty=nameWithType> e <xref:System.String?displayProperty=nameWithType> sono tutti non modificabili. Il modificatore di sola lettura in un campo di tipo riferimento impedisce che l'istanza archiviata nel campo venga sostituita, ma non impedisce la modifica dei dati dell'istanza del campo chiamando membri che modificano l'istanza.

 *Parti © 2005, 2009 Microsoft Corporation. Tutti i diritti riservati.*

 *Ristampato con l'autorizzazione di Pearson Education, Inc. da [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2a edizione](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) di Krzysztof Cwalina and Brad Abrams, pubblicato il 22 ottobre 2008 da Addison-Wesley Professional nella collana Microsoft Windows Development Series.*

## <a name="see-also"></a>Vedere anche

- [Linee guida per la progettazione di membri](member.md)
- [Linee guida per la progettazione di Framework](index.md)
