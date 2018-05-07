---
title: Distribuzione di applicazioni WCF con ClickOnce
ms.date: 03/30/2017
ms.assetid: 1a11feee-2a47-4d3e-a28a-ad69d5ff93e0
ms.openlocfilehash: ceb652eed1a7cc377538f5d693dcb85ed99da4b3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="deploying-wcf-applications-with-clickonce"></a>Distribuzione di applicazioni WCF con ClickOnce
Applicazioni client utilizzando Windows Communication Foundation (WCF) possono essere distribuite tramite la tecnologia ClickOnce. Questa tecnologia consente loro di avvalersi delle protezioni runtime fornite dalla protezione dall'accesso di codice, purché siano firmate digitalmente con un certificato attendibile. Il certificato utilizzato per firmare l'applicazione ClickOnce deve risiedere nell'archivio autori attendibili e il criterio di sicurezza locale nel computer client deve essere configurato per concedere autorizzazioni di attendibilità totale alle applicazioni firmate con il certificato dell'autore.  
  
 Per informazioni sulla configurazione di applicazioni ClickOnce e autori attendibili, vedere [la configurazione di editori attendibili ClickOnce](http://go.microsoft.com/fwlink/?LinkId=94774).  
  
## <a name="see-also"></a>Vedere anche  
 [Panoramica della distribuzione di applicazioni attendibili](http://go.microsoft.com/fwlink/?LinkId=94775)  
 [Applicazioni di distribuzione ClickOnce per Windows Form](http://go.microsoft.com/fwlink/?LinkId=94776)
