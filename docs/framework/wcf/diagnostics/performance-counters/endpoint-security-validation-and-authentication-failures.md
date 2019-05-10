---
title: 'Endpoint: Errori di convalida e di autenticazione della protezione'
ms.date: 03/30/2017
ms.assetid: 5bad60aa-6084-4c7b-aefd-9b581f04382e
ms.openlocfilehash: 9e0192ea600bb52abd555f2f83cfe8e96d3fe203
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64619333"
---
# <a name="endpoint-security-validation-and-authentication-failures"></a>Endpoint: Errori di convalida e di autenticazione della protezione
Nome contatore: Errori di convalida e di autenticazione della protezione  
  
## <a name="description"></a>Descrizione  
 Questo contatore avanza ogni volta che un messaggio viene rifiutato a causa di un problema di sicurezza non coperto dal contatore "chiamate di sicurezza non autorizzate". Tra tali problemi si contano:  
  
- Non è stato possibile leggere il token client dal messaggio.  
  
- Il client token non è stato autenticato (la password era errata).  
  
- La verifica della firma non è riuscita (il messaggio è stato manomesso).  
  
- Il messaggio è un duplicato di un messaggio precedente. Ciò può verificarsi durante un attacco di tipo replay.  
  
- Si è verificato un errore di decrittografia.  
  
- Alcuni elementi obbligatori (un timestamp o un blocco di dati crittografati) non sono presenti nel messaggio.  
  
- Gli errori si sono verificati durante l'handshake TLSNEGO/SPNEGO.
