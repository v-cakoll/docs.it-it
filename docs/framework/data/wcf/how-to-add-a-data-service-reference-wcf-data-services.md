---
title: 'Procedura: Aggiungere un riferimento al servizio dati (WCF Data Services)'
ms.date: 08/24/2018
helpviewer_keywords:
- WCF Data Services, configuring
ms.assetid: 62c6f318-3ee1-433a-b7a3-efa234c3034c
ms.openlocfilehash: 42d89cf87b5fe9bbdb229f10cd6a0e340d4c08fd
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70790747"
---
# <a name="how-to-add-a-data-service-reference-wcf-data-services"></a>Procedura: Aggiungere un riferimento al servizio dati (WCF Data Services)

Per aggiungere un riferimento a WCF Data Services, è possibile usare la finestra di dialogo **Aggiungi riferimento al servizio** in Visual Studio. In questo modo è possibile accedere più facilmente a un servizio dati in un'applicazione client sviluppata in Visual Studio. Al completamento di questa procedura, verranno generate classi di dati in base ai metadati ottenuti dal servizio dati. Per ulteriori informazioni, vedere [generazione della libreria client del servizio dati](generating-the-data-service-client-library-wcf-data-services.md).

## <a name="add-a-data-service-reference"></a>Aggiungere un riferimento al servizio dati

1. (Facoltativo) Se il servizio dati non fa parte della soluzione e non è già in esecuzione, avviare il servizio dati e prendere nota dell'URI del servizio dati.

2. In Visual Studio, in **Esplora soluzioni**, fare clic con il pulsante destro del mouse sul progetto client, quindi scegliere **Aggiungi** > **riferimento al servizio**.

3. Se il servizio dati fa parte della soluzione corrente, fare clic su **individua**.

     -oppure-

     Nella casella di testo **Indirizzo** Digitare l'URL di base del servizio dati, ad esempio `http://localhost:1234/Northwind.svc`, e quindi fare clic su **Vai**.

4. Selezionare **OK**.

     Al progetto viene aggiunto un nuovo file di codice che contiene le classi di dati che possono accedere e interagire con le risorse del servizio dati.

## <a name="see-also"></a>Vedere anche

- [Guida rapida](quickstart-wcf-data-services.md)
