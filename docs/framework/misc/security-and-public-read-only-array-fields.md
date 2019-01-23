---
title: Sicurezza e campi di matrice pubblici di sola lettura
ms.date: 03/30/2017
helpviewer_keywords:
- security [.NET Framework], public read-only array fields
ms.assetid: 3df28dee-2a9f-40ff-9852-bfdbe59c27f3
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 03f3ce51eaab9e08d5f05932d9360adc4fd2110f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54560987"
---
# <a name="security-and-public-read-only-array-fields"></a>Sicurezza e campi di matrice pubblici di sola lettura
Consente di utilizzare mai i campi di matrice pubblica di sola lettura dalla librerie gestite per definire il comportamento del limite o la sicurezza delle applicazioni perché i campi di matrice pubblica di sola lettura possono essere modificati.  
  
## <a name="remarks"></a>Note  
 Alcune classi di .NET framework includono campi pubblici di sola lettura che contengono parametri di limiti specifici della piattaforma.  Ad esempio, il <xref:System.IO.Path.InvalidPathChars> campo è una matrice che descrive i caratteri non consentiti in una stringa di percorso di file.  Numero di campi simili è presenti in tutto .NET Framework.  
  
 I valori dei campi pubblici di sola lettura come <xref:System.IO.Path.InvalidPathChars> può essere modificato dal codice o dal codice che condivide il dominio dell'applicazione.  Non si utilizzino i campi di matrice pubblica di sola lettura simile al seguente per definire il comportamento del limite delle applicazioni.  In caso contrario codice dannoso può modificare le definizioni dei limiti e usare il codice in modo imprevisto.  
  
 Nella versione 2.0 e versioni successive di .NET Framework, è necessario usare i metodi che restituiscono una nuova matrice invece di usare i campi pubblici.  Ad esempio, invece di usare la <xref:System.IO.Path.InvalidPathChars> campo, è consigliabile usare il <xref:System.IO.Path.GetInvalidPathChars%2A> (metodo).  
  
 Si noti che i tipi di .NET Framework non utilizzano i campi pubblici per definire tipi di limite internamente.  Al contrario, .NET Framework Usa separati campi privati.  Modifica dei valori di questi campi pubblici non modifica il comportamento dei tipi .NET Framework.  
  
## <a name="see-also"></a>Vedere anche
- [Linee guida per la generazione di codice sicuro](../../../docs/standard/security/secure-coding-guidelines.md)
