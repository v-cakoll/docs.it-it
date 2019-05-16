---
title: 'Procedura: Aggiungere un riferimento al servizio dati (WCF Data Services)'
ms.date: 08/24/2018
helpviewer_keywords:
- WCF Data Services, configuring
ms.assetid: 62c6f318-3ee1-433a-b7a3-efa234c3034c
ms.openlocfilehash: 8bf623ec74c3bd165f63f60e883bfcb532d6900b
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2019
ms.locfileid: "65633950"
---
# <a name="how-to-add-a-data-service-reference-wcf-data-services"></a>Procedura: Aggiungere un riferimento al servizio dati (WCF Data Services)

È possibile usare la **Aggiungi riferimento al servizio** finestra di dialogo in Visual Studio per aggiungere un riferimento a WCF Data Services. In questo modo è possibile accedere più facilmente a un servizio dati in un'applicazione client sviluppata in Visual Studio. Al completamento di questa procedura, verranno generate classi di dati in base ai metadati ottenuti dal servizio dati. Per altre informazioni, vedere [generazione della libreria Client di servizio dati](../../../../docs/framework/data/wcf/generating-the-data-service-client-library-wcf-data-services.md).

## <a name="add-a-data-service-reference"></a>Aggiungere un riferimento al servizio dati

1. (Facoltativo) Se il servizio dati non fa parte della soluzione e non è già in esecuzione, avviare il servizio dati e prendere nota dell'URI del servizio dati.

2. In Visual Studio, in **Esplora soluzioni**, fare clic sul progetto client e quindi selezionare **Add** > **riferimento al servizio**.

3. Se il servizio dati fa parte della soluzione corrente, fare clic su **Discover**.

     -oppure-

     Nel **indirizzi** nella casella di testo digitare l'URL di base del servizio dati, ad esempio `http://localhost:1234/Northwind.svc`, quindi fare clic su **passare**.

4. Scegliere **OK**.

     Un nuovo file di codice che contiene le classi di dati che possono accedere e interagire con le risorse del servizio dati viene aggiunto al progetto.

## <a name="see-also"></a>Vedere anche

- [Guida rapida](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md)
