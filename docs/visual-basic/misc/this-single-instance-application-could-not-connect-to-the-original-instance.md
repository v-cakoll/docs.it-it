---
title: Impossibile connettere l'applicazione a istanza singola con l'istanza originale
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbrAppModel_SingleInstanceCantConnect
ms.assetid: 7c2c0cee-02a1-4157-be03-39d18e18408f
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 9cb8cef696ba93f922dfe0d92195a5fb5147b4cc
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/21/2017
---
# <a name="this-single-instance-application-could-not-connect-to-the-original-instance"></a>Impossibile connettere l'applicazione a istanza singola con l'istanza originale
Impossibile connettere l'applicazione a istanza singola con l'istanza originale. Alcune possibili cause di questo problema sono le seguenti:  
  
-   L'istanza originale attualmente non risponde.  
  
-   L'applicazione non dispone di autorizzazioni per la creazione di oggetti del kernel. Per ulteriori informazioni sugli oggetti kernel, vedere [mutex](../../standard/threading/mutexes.md).  
  
     Il nome base degli oggetti del kernel deriva dalla concatenazione del GUID dell'assembly, del numero di versione principale e del numero di versione secondario. Il nome base ad esempio potrebbe essere `3639f15d-9547-43da-8145-60da347829915.1`.  
  
## <a name="to-correct-this-error-when-developing-the-application"></a>Per correggere questo errore quando si sviluppa l'applicazione  
  
1.  Verificare che l'applicazione non passi allo stato di non reattività.  
  
2.  Verificare che l'applicazione abbia autorizzazioni sufficienti per creare oggetti kernel.  
  
3.  Riavviare l'istanza originale dell'applicazione.  
  
4.  Riavviare il computer per cancellare i processi che stanno usando la risorsa necessaria per la connessione all'istanza originale.  
  
5.  Prendere nota delle circostanze in cui si è verificato l'errore e chiamare il Servizio supporto tecnico Microsoft.  
  
## <a name="see-also"></a>Vedere anche  
 [Debugger Basics](/visualstudio/debugger/debugger-basics) (Nozioni di base sul debugger)  

