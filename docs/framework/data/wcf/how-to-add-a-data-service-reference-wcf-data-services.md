---
title: 'Procedura: aggiungere un riferimento al servizio dati (WCF Data Services)'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework-oob
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: WCF Data Services, configuring
ms.assetid: 62c6f318-3ee1-433a-b7a3-efa234c3034c
caps.latest.revision: "2"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: a8fb075bdb17f0d562d752bc4125141bb0bb2ab9
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-add-a-data-service-reference-wcf-data-services"></a>Procedura: aggiungere un riferimento al servizio dati (WCF Data Services)
È possibile utilizzare il **Aggiungi riferimento al servizio** finestra di dialogo in Visual Studio per aggiungere un riferimento a [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]. In questo modo è possibile accedere più facilmente a un servizio dati in un'applicazione client sviluppata in Visual Studio. Al completamento di questa procedura, verranno generate classi di dati in base ai metadati ottenuti dal servizio dati. Per ulteriori informazioni, vedere [la generazione della libreria Client del servizio dati](../../../../docs/framework/data/wcf/generating-the-data-service-client-library-wcf-data-services.md).  
  
### <a name="to-add-a-data-service-reference"></a>Per aggiungere un riferimento al servizio dati  
  
1.  (Facoltativo) Se il servizio dati non fa parte della soluzione e non è già in esecuzione, avviare il servizio dati e prendere nota dell'URI del servizio dati.  
  
2.  Fare clic sul progetto client e quindi selezionare **Aggiungi riferimento al servizio**.  
  
3.  Se il servizio dati fa parte della soluzione corrente, fare clic su **Discover**.  
  
     -oppure-  
  
     Nel **indirizzo** nella casella di testo digitare l'URL di base del servizio dati, ad esempio `http://localhost:1234/Northwind.svc`, quindi fare clic su **passare**.  
  
4.  Fare clic su **OK**.  
  
     Aggiunge un nuovo file di codice contenente le classi di dati usate per accedere e interagire con le risorse del servizio dati come oggetti.  
  
## <a name="see-also"></a>Vedere anche  
 [Guida rapida](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md)
