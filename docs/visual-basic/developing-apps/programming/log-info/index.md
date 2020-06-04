---
title: Registrazione di informazioni relative all'applicazione
ms.date: 07/20/2015
helpviewer_keywords:
- Log object
- My.Log object
- applications [Visual Basic], logging information from
- logging
- My.Application.Log object
- examples [Visual Basic], logging application information
ms.assetid: 8bf4f047-22d6-48d6-aec5-93b98ad5b8e8
ms.openlocfilehash: 43738b2d654435532a98654cbc40af134d43f02c
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84410023"
---
# <a name="logging-information-from-the-application-visual-basic"></a>Registrazione di informazioni relative all'applicazione (Visual Basic)

Questa sezione contiene argomenti che descrivono come registrare le informazioni provenienti dall'applicazione usando l'oggetto `My.Application.Log` o `My.Log`. Viene anche spiegato come estendere le funzionalità di registrazione dell'applicazione.  
  
 L'oggetto `Log` fornisce i metodi per scrivere le informazioni sui listener di log dell'applicazione, mentre la proprietà avanzata `TraceSource` dell'oggetto `Log` fornisce informazioni di configurazione dettagliate. L'oggetto `Log` può essere configurato dal file di configurazione dell'applicazione.  
  
 L'oggetto `My.Log` è disponibile solo per le applicazioni ASP.NET. Per le applicazioni client, usare `My.Application.Log`. Per altre informazioni, vedere <xref:Microsoft.VisualBasic.Logging.Log>.  
  
## <a name="tasks"></a>Attività  
  
|A|Vedere|  
|--------|---------|  
|Scrivere le informazioni sugli eventi nei log dell'applicazione.|[Procedura: Scrivere messaggi di log](how-to-write-log-messages.md)|  
|Scrivere le informazioni sulle eccezioni nei log dell'applicazione.|[Procedura: Registrare eccezioni](how-to-log-exceptions.md)|  
|Scrivere le informazioni di traccia nei log dell'applicazione all'avvio e alla chiusura dell'applicazione.|[Procedura: Registrare messaggi all'avvio o all'arresto dell'applicazione](how-to-log-messages-when-the-application-starts-or-shuts-down.md)|  
|Configurare `My.Application.Log` per scrivere le informazioni in un file di testo.|[Procedura: Scrivere informazioni sugli eventi in un file di testo](how-to-write-event-information-to-a-text-file.md)|  
|Configurare `My.Application.Log` per scrivere le informazioni in un log eventi.|[Procedura: Scrivere nel log eventi di un'applicazione](how-to-write-to-an-application-event-log.md)|  
|Modificare la posizione in cui `My.Application.Log` scrive le informazioni.|[Procedura dettagliata: Modifica della posizione di inserimento delle informazioni con My.Application.Log](walkthrough-changing-where-my-application-log-writes-information.md)|  
|Determinare la posizione in cui `My.Application.Log` scrive le informazioni.|[Procedura dettagliata: Individuazione della posizione di inserimento delle informazioni con My.Application.Log](walkthrough-determining-where-my-application-log-writes-information.md)|  
|Creare un listener di log personalizzato per `My.Application.Log`.|[Procedura dettagliata: Creazione di listener di log personalizzati](walkthrough-creating-custom-log-listeners.md)|  
|Filtrare l'output dei log `My.Application.Log`.|[Procedura dettagliata: Filtro dell'output di My.Application.Log](walkthrough-filtering-my-application-log-output.md)|  
  
## <a name="see-also"></a>Vedere anche

- <xref:Microsoft.VisualBasic.Logging.Log?displayProperty=nameWithType>
- [Utilizzo dei log applicazione](working-with-application-logs.md)
- [Risoluzione dei problemi: Listener di log](troubleshooting-log-listeners.md)
