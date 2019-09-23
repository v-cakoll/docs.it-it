---
title: Configurazione centralizzata
description: La configurazione centralizzata con Azure Key Vault può semplificare la gestione delle app native del cloud.
ms.date: 06/30/2019
ms.openlocfilehash: f4f495591550abccf2c64ef24cbe7620b039d8ca
ms.sourcegitcommit: 55f438d4d00a34b9aca9eedaac3f85590bb11565
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/23/2019
ms.locfileid: "71183518"
---
# <a name="centralized-configuration"></a>Configurazione centralizzata

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

Le applicazioni native del cloud coinvolgono molti altri servizi in esecuzione rispetto alle tradizionali app monolitiche a istanza singola. La gestione delle impostazioni di configurazione per decine di servizi interdipendenti può essere complessa, motivo per cui gli archivi di configurazione centralizzati vengono spesso implementati per le applicazioni distribuite.

Come illustrato nel [capitolo 1](introduction.md), le raccomandazioni per le app a dodici fattori richiedono una separazione rigorosa tra il codice e la configurazione. Questo significa che l'archiviazione delle impostazioni di configurazione come costanti o valori letterali nel codice è una violazione. Questa raccomandazione esiste perché lo stesso codice deve essere utilizzato in più ambienti, tra cui sviluppo, test, gestione temporanea e produzione. Tuttavia, è probabile che i valori di configurazione variano a seconda di ognuno di questi ambienti. I valori di configurazione devono quindi essere archiviati nell'ambiente stesso oppure l'ambiente deve archiviare le credenziali in un archivio di configurazione centralizzato.

L'applicazione eShopOnContainers include i file di impostazioni dell'applicazione locale con ogni microservizio. Questi file vengono archiviati nel controllo del codice sorgente, ma non includono i segreti di produzione, ad esempio le stringhe di connessione o le chiavi API. In produzione, le singole impostazioni possono essere sovrascritte con le variabili di ambiente per servizio. Si tratta di una pratica comune per le applicazioni ospitate, ma non fornisce un archivio di configurazione centrale. Per supportare la gestione centralizzata delle impostazioni di configurazione, ogni microservizio include un'impostazione che consente di alternare l'uso di impostazioni locali o Azure Key Vault impostazioni.

## <a name="azure-key-vault"></a>Azure Key Vault

Azure Key Vault offre archiviazione sicura di token, password, certificati, chiavi API e altri segreti riservati. L'accesso a Key Vault richiede l'autenticazione e l'autorizzazione del chiamante appropriate, che nel caso dei microservizi eShopOnContainers indica l'uso di una combinazione ClientID/ClientSecret. Non archiviare le credenziali nel controllo del codice sorgente, ma impostate nell'ambiente dell'applicazione. L'accesso diretto a Key Vault da AKS può essere eseguito usando [Key Vault FlexVolume](https://github.com/Azure/kubernetes-keyvault-flexvol).

Con la configurazione centralizzata, le impostazioni che si applicano all'intera applicazione, ad esempio l'endpoint di registrazione centralizzato, possono essere impostate una sola volta e utilizzate da ogni parte dell'applicazione distribuita. Sebbene i microservizi siano indipendenti l'uno dall'altro, in genere saranno presenti alcune dipendenze condivise i cui dettagli di configurazione possono trarre vantaggio da un archivio di configurazione centralizzato.

>[!div class="step-by-step"]
>[Precedente](deploy-eshoponcontainers-azure.md)
>[Successivo](scale-applications.md) <!-- Next Chapter -->
