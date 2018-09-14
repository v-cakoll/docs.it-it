---
title: Distribuzione di applicazioni WCF con ClickOnce
ms.date: 03/30/2017
ms.assetid: 1a11feee-2a47-4d3e-a28a-ad69d5ff93e0
ms.openlocfilehash: d733c6f523393737418c6394707c1d4e6e9c1710
ms.sourcegitcommit: 76a304c79a32aa13889ebcf4b9789a4542b48e3e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/13/2018
ms.locfileid: "45529081"
---
# <a name="deploying-wcf-applications-with-clickonce"></a>Distribuzione di applicazioni WCF con ClickOnce
Le applicazioni client tramite Windows Communication Foundation (WCF) possono essere distribuite tramite la tecnologia ClickOnce. Questa tecnologia consente loro di avvalersi delle protezioni runtime fornite dalla protezione dall'accesso di codice, purché siano firmate digitalmente con un certificato attendibile. Il certificato utilizzato per firmare l'applicazione ClickOnce deve risiedere nell'archivio autori attendibili e il criterio di sicurezza locale nel computer client deve essere configurato per concedere autorizzazioni di attendibilità totale alle applicazioni firmate con il certificato dell'autore.  
  
 Per informazioni sulla configurazione di applicazioni ClickOnce e autori attendibili, vedere [configurazione di editori attendibili ClickOnce](https://go.microsoft.com/fwlink/?LinkId=94774).  
  
## <a name="see-also"></a>Vedere anche  
 [Panoramica della distribuzione di applicazioni attendibili](https://go.microsoft.com/fwlink/?LinkId=94775)  
 [Distribuzione ClickOnce per Windows Forms Application](https://go.microsoft.com/fwlink/?LinkId=94776)
