---
title: Distribuzione di applicazioni WCF con ClickOnce
ms.date: 03/30/2017
ms.assetid: 1a11feee-2a47-4d3e-a28a-ad69d5ff93e0
ms.openlocfilehash: 1820b00aa903633750f74f319f9cf8038ba2b043
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59086234"
---
# <a name="deploying-wcf-applications-with-clickonce"></a>Distribuzione di applicazioni WCF con ClickOnce
Le applicazioni client tramite Windows Communication Foundation (WCF) possono essere distribuite tramite la tecnologia ClickOnce. Questa tecnologia consente loro di avvalersi delle protezioni runtime fornite dalla protezione dall'accesso di codice, purché siano firmate digitalmente con un certificato attendibile. Il certificato utilizzato per firmare l'applicazione ClickOnce deve risiedere nell'archivio autori attendibili e il criterio di sicurezza locale nel computer client deve essere configurato per concedere autorizzazioni di attendibilità totale alle applicazioni firmate con il certificato dell'autore.  
  
 Per informazioni sulla configurazione di applicazioni ClickOnce e autori attendibili, vedere [configurazione di editori attendibili ClickOnce](https://go.microsoft.com/fwlink/?LinkId=94774).  
  
## <a name="see-also"></a>Vedere anche

- [Panoramica della distribuzione di applicazioni attendibili](https://go.microsoft.com/fwlink/?LinkId=94775)
- [Distribuzione ClickOnce per Windows Forms Application](https://go.microsoft.com/fwlink/?LinkId=94776)
