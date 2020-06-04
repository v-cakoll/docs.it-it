---
title: Oggetti
ms.date: 07/20/2015
helpviewer_keywords:
- objects [Visual Basic]
ms.assetid: 651c73e4-dca8-402b-9c6b-e3902b3a3f4b
ms.openlocfilehash: e927f69b7606866a0a9e8eadd59270f51ffc5e2b
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84414220"
---
# <a name="objects-visual-basic"></a>Oggetti (Visual Basic)
Questo argomento contiene collegamenti ad altri argomenti che illustrano gli oggetti runtime di Visual Basic e contengono tabelle di procedure, proprietà ed eventi dei relativi membri.  
  
## <a name="visual-basic-run-time-objects"></a>Oggetti runtime di Visual Basic  
  
|||  
|---|---|  
|<xref:Microsoft.VisualBasic.Collection>|Rappresenta un modo pratico di visualizzare un gruppo correlato di elementi come un singolo oggetto.|  
|<xref:Microsoft.VisualBasic.Information.Err%2A>|Contiene informazioni sugli errori di runtime.|  
|L'oggetto `My.Application` è costituito dalle classi seguenti:<br /><br /> <xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase> specifica i membri disponibili in tutti i progetti.<br /><br /> <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase> specifica i membri disponibili nelle applicazioni Windows Form.<br /><br /> <xref:Microsoft.VisualBasic.ApplicationServices.ConsoleApplicationBase> specifica i membri disponibili nelle applicazioni console.|Specifica i dati associati solo all'applicazione o DLL corrente. Nessuna informazione a livello di sistema può essere modificata con `My.Application`.<br /><br /> Alcuni membri sono disponibili solo per le applicazioni console o Windows Form.|  
|`My.Application.Info` (<xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase.Info%2A>)|Specifica le proprietà necessarie per ottenere le informazioni relative a un'applicazione, ad esempio il numero di versione, la descrizione, gli assembly caricati e così via.|  
|`My.Application.Log` (<xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase.Log%2A>)|Fornisce una proprietà e i metodi per scrivere le informazioni relative a eventi ed eccezioni nei listener di log dell'applicazione.|  
|`My.Computer` (<xref:Microsoft.VisualBasic.Devices.Computer>)|Specifica le proprietà per la modifica dei componenti del computer, ad esempio audio, orologio, tastiera, file system e così via.|  
|`My.Computer.Audio` (<xref:Microsoft.VisualBasic.Devices.Audio>)|Specifica i metodi per la riproduzione di suoni.|  
|`My.Computer.Clipboard` (<xref:Microsoft.VisualBasic.Devices.Computer.Clipboard%2A>)|Specifica i metodi per la modifica degli Appunti.|  
|`My.Computer.Clock` (<xref:Microsoft.VisualBasic.Devices.Clock>)|Offre proprietà che consentono di accedere all'ora locale corrente e all'ora UTC (Universal Coordinated Time), equivalente all'ora di Greenwich, dal clock di sistema.|  
|`My.Computer.FileSystem` (<xref:Microsoft.VisualBasic.FileIO.FileSystem>)|Specifica proprietà e metodi per l'uso di unità, file e directory.|  
|`My.Computer.FileSystem.SpecialDirectories` (<xref:Microsoft.VisualBasic.FileIO.SpecialDirectories>)|Specifica le proprietà per l'accesso alle directory a cui si fa comunemente riferimento.|  
|`My.Computer.Info` (<xref:Microsoft.VisualBasic.Devices.ComputerInfo>)|Offre proprietà che consentono di ottenere informazioni su memoria del computer, assembly caricati, nome e sistema operativo.|  
|`My.Computer.Keyboard` (<xref:Microsoft.VisualBasic.Devices.Keyboard>)|Offre proprietà che consentono di accedere allo stato corrente della tastiera, per sapere ad esempio quali tasti vengono attualmente premuti, e un metodo per inviare le sequenze di tasti alla finestra attiva.|  
|`My.Computer.Mouse` (<xref:Microsoft.VisualBasic.Devices.Mouse>)|Offre proprietà che consentono di ottenere informazioni sul formato e sulla configurazione del mouse installato nel computer locale.|  
|`My.Computer.Network` (<xref:Microsoft.VisualBasic.Devices.Network>)|Specifica una proprietà, un evento e i metodi per l'interazione con la rete a cui è connesso il computer.|  
|`My.Computer.Ports` (<xref:Microsoft.VisualBasic.Devices.Ports>)|Specifica una proprietà e un metodo per l'accesso alle porte seriali del computer.|  
|`My.Computer.Registry` (<xref:Microsoft.VisualBasic.MyServices.RegistryProxy>)|Specifica proprietà e metodi per la modifica del Registro di sistema.|  
|[Oggetto My.Forms](my-forms-object.md)|Offre proprietà per l'accesso a un'istanza di ogni Windows Form dichiarato nel progetto corrente.|  
|`My.Log` (<xref:Microsoft.VisualBasic.Logging.AspLog>)|Specifica una proprietà e i metodi per la scrittura di informazioni relative a eventi ed eccezioni nei listener di log dell'applicazione per le applicazioni Web.|  
|[Oggetto My.Request](my-request-object.md)|Ottiene l'oggetto <xref:System.Web.HttpRequest> per la pagina richiesta. L'oggetto `My.Request` contiene informazioni sulla richiesta HTTP corrente.<br /><br /> L'oggetto `My.Request` è disponibile solo per le applicazioni ASP.NET.|  
|[Oggetto My.Resources](my-resources-object.md)|Specifica proprietà e classi per l'accesso alle risorse di un'applicazione.|  
|[Oggetto My.Response](my-response-object.md)|Ottiene l'oggetto <xref:System.Web.HttpResponse> associato a <xref:System.Web.UI.Page>. Questo oggetto consente di inviare dati di risposta HTTP a un client e contiene informazioni su tale risposta.<br /><br /> L'oggetto `My.Response` è disponibile solo per le applicazioni ASP.NET.|  
|[Oggetto My.Settings](my-settings-object.md)|Specifica proprietà e metodi per l'accesso alle impostazioni di un'applicazione.|  
|`My.User` (<xref:Microsoft.VisualBasic.ApplicationServices.User>)|Offre l'accesso alle informazioni sull'utente corrente.|  
|[Oggetto My.WebServices](my-webservices-object.md)|Specifica le proprietà per la creazione e l'accesso a una singola istanza di ogni servizio Web a cui fa riferimento il progetto corrente.|  
|<xref:Microsoft.VisualBasic.FileIO.TextFieldParser>|Fornisce i metodi e le proprietà per l'analisi dei file di testo strutturati.|  
  
## <a name="see-also"></a>Vedere anche

- [Riferimenti al linguaggio Visual Basic](../index.md)
