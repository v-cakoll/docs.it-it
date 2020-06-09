---
title: System.ServiceModel.MessageClosedAgain
ms.date: 03/30/2017
ms.assetid: 24c274d4-65cd-4c91-9869-bc6eb34ef979
ms.openlocfilehash: d341953b8e12b14e6a3fe8a477c16a1b3a4454ae
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84580437"
---
# <a name="systemservicemodelmessageclosedagain"></a>System.ServiceModel.MessageClosedAgain
System.ServiceModel.MessageClosedAgain  
  
## <a name="description"></a>Descrizione  
 Un messaggio è stato nuovamente chiuso.  
  
 Un messaggio deve essere chiuso solo una volta. Se questa traccia viene emessa in codice di estensione utente, indica che tale codice sta chiudendo un messaggio che è già stato chiuso. Se viene emessa tramite codice del prodotto, indica che il codice di estensione utente potrebbe potenzialmente stare per chiudere un messaggio troppo presto.  
  
## <a name="see-also"></a>Vedere anche

- [Traccia](index.md)
- [Utilizzo delle tracce per risolvere i problemi di un'applicazione](using-tracing-to-troubleshoot-your-application.md)
- [Amministrazione e diagnostica](../index.md)
