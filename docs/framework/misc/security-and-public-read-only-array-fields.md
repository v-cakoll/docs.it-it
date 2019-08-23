---
title: Sicurezza e campi di matrice pubblici di sola lettura
ms.date: 03/30/2017
helpviewer_keywords:
- security [.NET Framework], public read-only array fields
ms.assetid: 3df28dee-2a9f-40ff-9852-bfdbe59c27f3
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 3d36009fa4fc7b9299708768fe34a75f1fde6797
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69910729"
---
# <a name="security-and-public-read-only-array-fields"></a>Sicurezza e campi di matrice pubblici di sola lettura
Non usare mai i campi di matrice pubblica di sola lettura dalle librerie gestite per definire il comportamento dei limiti o la sicurezza delle applicazioni perché è possibile modificare i campi di matrice pubblica di sola lettura.  
  
## <a name="remarks"></a>Note  
 Alcune classi di .NET Framework includono campi pubblici di sola lettura che contengono parametri limite specifici della piattaforma.  Ad esempio, il <xref:System.IO.Path.InvalidPathChars> campo è una matrice che descrive i caratteri non consentiti in una stringa di percorso file.  In .NET Framework sono presenti molti campi simili.  
  
 I valori dei campi di sola lettura pubblici come <xref:System.IO.Path.InvalidPathChars> possono essere modificati dal codice o dal codice che condivide il dominio applicazione del codice.  Non usare campi di matrice pubblica di sola lettura come questo per definire il comportamento dei limiti delle applicazioni.  In tal caso, il codice dannoso può modificare le definizioni dei limiti e usare il codice in modi imprevisti.  
  
 Nella versione 2,0 e successive del .NET Framework, è consigliabile usare metodi che restituiscono una nuova matrice anziché usare campi di matrice pubblici.  Ad esempio, invece di usare il <xref:System.IO.Path.InvalidPathChars> campo, è necessario usare il <xref:System.IO.Path.GetInvalidPathChars%2A> metodo.  
  
 Si noti che i tipi di .NET Framework non usano i campi pubblici per definire i tipi di limite internamente.  Il .NET Framework utilizza invece campi privati distinti.  La modifica dei valori di questi campi pubblici non comporta la modifica del comportamento dei tipi di .NET Framework.  
  
## <a name="see-also"></a>Vedere anche

- [Linee guida per la generazione di codice sicuro](../../standard/security/secure-coding-guidelines.md)
