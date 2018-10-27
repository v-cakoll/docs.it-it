---
title: 'Endpoint: errori di convalida di sicurezza e di autenticazione al secondo'
ms.date: 03/30/2017
ms.assetid: 89a70b90-d7e4-4b03-9b84-4dc88ce3d605
ms.openlocfilehash: 43886f79585fb9a63eeb51360cc869365c100a1d
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2018
ms.locfileid: "50191641"
---
# <a name="endpoint-security-validation-and-authentication-failures-per-second"></a>Endpoint: errori di convalida di sicurezza e di autenticazione al secondo
Nome contatore: errori di convalida di sicurezza e di autenticazione al secondo  
  
## <a name="description"></a>Descrizione  
 Questo contatore avanza ogni volta che un messaggio viene rifiutato a causa di un problema di sicurezza non coperto dal contatore "chiamate di sicurezza non autorizzate". Tra tali problemi si contano:  
  
-   Non è stato possibile leggere il token client dal messaggio.  
  
-   Il client token non è stato autenticato (ad esempio la password era errata).  
  
-   La verifica della firma non è riuscita (ad esempio il messaggio è stato manomesso).  
  
-   Il messaggio è un duplicato di un messaggio precedente. Ciò può verificarsi durante un attacco di tipo replay.  
  
-   Si è verificato un errore di decrittografia.  
  
-   Alcuni elementi obbligatori (ad esempio timestamp mancante o blocco di dati crittografati) non sono presenti nel messaggio.  
  
-   Gli errori si sono verificati durante l'handshake TLSNEGO/SPNEGO.  
  
 Questo contatore è di tipo di contatore delle prestazioni [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), il cui valore viene calcolato utilizzando la formula seguente:  
  
 (N1-N0)/((D1-D0)/F)
