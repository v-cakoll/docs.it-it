---
title: Istruzioni per l'hosting su IIS (Internet Information Services)
ms.date: 03/30/2017
ms.assetid: 959a21c8-9d9d-4757-b255-4e57793ae9d6
ms.openlocfilehash: 5d315fa482e423461eab171a19746b6ea792aac5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33507574"
---
# <a name="internet-information-service-hosting-instructions"></a>Istruzioni per l'hosting su IIS (Internet Information Services)
Per eseguire gli esempi ospitati su Internet Information Services (IIS) è necessario assicurarsi che IIS sia installato correttamente e sia in esecuzione.  
  
### <a name="to-install-iis-version-75-on-windows-server-2008-r2"></a>Installazione di IIS versione 7.5 in Windows Server 2008 R2  
  
1.  Dal **Server Manager**, selezionare **ruoli.** In **Riepilogo ruoli**, fare clic su **Aggiungi ruoli**.  
  
2.  Fare clic su **Avanti** per visualizzare il **Selezione ruoli Server** finestra di dialogo.  
  
3.  Selezionare **Server applicazioni** dal **ruoli** elenco e quindi fare clic su **Avanti** due volte per visualizzare il **Selezione servizi ruolo** finestra di dialogo per il Ruolo Server applicazioni.  
  
4.  Selezionare il **Server Web (IIS)** casella di controllo. Se viene chiesto di installare ulteriori servizi ruolo e funzionalità, fare clic su **Aggiungi funzionalità necessarie**. Fare clic su **Avanti** due volte per visualizzare il **Selezione servizi ruolo** finestra di dialogo per il ruolo Server Web (IIS).  
  
5.  Espandere **gli strumenti di gestione**, quindi espandere **compatibilità Gestione IIS 6**. Selezionare **IIS strumenti di Scripting 6**. Se viene chiesto di installare ulteriori servizi ruolo e funzionalità, fare clic su **Aggiungi servizi ruolo necessari**. Scegliere **Avanti**.  
  
6.  Se il riepilogo delle selezioni è corretto, fare clic su **installare**.  
  
7.  Al termine dell'installazione, fare clic su **Chiudi**.  
  
### <a name="to-install-iis-version-75-on-windows-7"></a>Per installare IIS versione 7.5 in Windows 7  
  
1.  Fare clic su **avviare**, quindi fare clic su **Pannello di controllo**.  
  
2.  Aprire il **programmi** gruppo.  
  
3.  In **programmi e funzionalità**, fare clic su **funzionalità di Windows di attivare o disattivare**.  
  
4.  Il **controllo dell'Account utente** viene visualizzata una finestra di dialogo. Scegliere **Continua**.  
  
5.  Il **le funzionalità di Windows** viene visualizzata una finestra di dialogo. Espandere l'elemento **Internet Information Services**.  
  
6.  Espandere l'elemento **servizi World Wide Web**.  
  
7.  Espandere l'elemento **funzionalità per lo sviluppo di applicazioni**.  
  
8.  Verificare che gli elementi seguenti siano selezionati:  
  
    1.  **Estendibilità .NET**  
  
    2.  **ASP.NET 2.0**  
  
    3.  **Estensioni ISAPI**  
  
    4.  **Filtri ISAPI**  
  
9. Nell'elemento **servizi World Wide Web**, espandere **funzionalità Http comuni**.  
  
10. Assicurarsi che **contenuto statico** è selezionata.  
  
11. Nell'elemento **servizi World Wide Web**, espandere **sicurezza**.  
  
12. Assicurarsi che **l'autenticazione di Windows** è selezionata.  
  
13. Sotto il **Internet Information Services** directory, espandere l'elemento **strumenti di gestione Web**, quindi selezionare **Console di gestione IIS**.  
  
14. Espandere l'elemento **compatibilità Gestione IIS 6**, quindi selezionare **strumenti di Scripting di IIS 6**.  
  
15. Sotto il **Internet Information Services** directory, espandere l'elemento **Microsoft .NET Framework 3.5.1**, quindi selezionare **Windows Communication Foundation Http Activation**.  
  
16. Fare clic su **OK**.  
  
### <a name="to-install-iis-version-70-on-windows-server-2008"></a>Installazione di IIS versione 7.0 in Windows Server 2008  
  
1.  Da **Server Manager**selezionare **ruoli**. In **Riepilogo ruoli**, fare clic su **Aggiungi ruoli**.  
  
2.  Fare clic su **Avanti** per visualizzare il **Selezione ruoli Server** finestra di dialogo.  
  
3.  Selezionare **Server applicazioni** dal **ruoli** elenco e quindi fare clic su **Avanti** due volte per visualizzare il **Selezione servizi ruolo** finestra di dialogo per il Ruolo Server applicazioni.  
  
4.  Selezionare **Server Web (IIS)** casella di controllo. Se viene chiesto di installare ulteriori servizi ruolo e funzionalità, fare clic su **Aggiungi funzionalità necessarie**. Fare clic su **Avanti** due volte per visualizzare il **Selezione servizi ruolo** finestra di dialogo per il ruolo Server Web (IIS).  
  
5.  Espandere **gli strumenti di gestione**, quindi espandere **compatibilità Gestione IIS 6**. Selezionare **IIS strumenti di Scripting 6**. Se viene chiesto di installare ulteriori servizi ruolo e funzionalità, fare clic su **Aggiungi servizi ruolo necessari**. Scegliere **Avanti**.  
  
6.  Se il riepilogo delle selezioni è corretto, fare clic su **installare**.  
  
7.  Al termine dell'installazione, fare clic su **Chiudi**.  
  
### <a name="to-install-iis-version-70-on-windows-vista"></a>Per installare IIS sulla versione 7.0 in Windows Vista  
  
1.  Fare clic sul pulsante Start, quindi scegliere Pannello di controllo.  
  
2.  Selezionare il **programmi** gruppo.  
  
3.  In **programmi e funzionalità**, fare clic su **funzionalità di Windows di attivare o disattivare**.  
  
4.  Il **controllo dell'Account utente** viene visualizzata una finestra di dialogo. Scegliere **Continua**.  
  
5.  Il **le funzionalità di Windows** viene visualizzata una finestra di dialogo. Espandere l'elemento **Internet Information Services**.  
  
6.  Espandere l'elemento **servizi World Wide Web**.  
  
7.  Espandere l'elemento **funzionalità per lo sviluppo di applicazioni**.  
  
8.  Verificare che gli elementi seguenti siano selezionati:  
  
    1.  **Estendibilità .NET**  
  
    2.  **ASP.NET 2.0**  
  
    3.  **Estensioni ISAPI**  
  
    4.  **Filtri ISAPI**  
  
9. Espandere l'elemento **strumenti di gestione Web**, quindi selezionare **Console di gestione IIS**.  
  
10. Nell'elemento **servizi World Wide Web**, espandere **funzionalità Http comuni**.  
  
11. Assicurarsi che **contenuto statico** è selezionata.  
  
12. Nell'elemento **servizi World Wide Web**, espandere **sicurezza**.  
  
13. Assicurarsi che **l'autenticazione di Windows** è selezionata.  
  
14. Espandere l'elemento **compatibilità Gestione IIS 6**, quindi selezionare **strumenti di Scripting di IIS 6**.  
  
15. Espandere l'elemento **Microsoft .NET Framework 3.0**, quindi selezionare **Windows Communication Foundation Http Activation**.  
  
16. Fare clic su**OK**.  
  
### <a name="to-install-iis-version-60-on-windows-server-2003"></a>Per installare IIS versione 6.0 in Windows Server 2003  
  
1.  Da **amministrazione Server**, fare clic su **Aggiungi o Rimuovi un ruolo**, quindi fare clic su **Avanti**.  
  
2.  Selezionare **server applicazioni (IIS, ASP.NET)** dal **ruolo Server** elenco e quindi fare clic su **Avanti**.  
  
3.  Selezionare **Abilita ASP.NET** casella di controllo e quindi fare clic su **Avanti**.  
  
4.  Se il riepilogo delle selezioni è corretto, fare clic su Avanti.  
  
### <a name="to-install-iis-version-51-on-windows-xp-with-service-pack-2-and-service-pack-3-installed"></a>Per installare IIS versione 5.1 in Windows XP con Service Pack 2 e Service Pack 3 installati  
  
1.  Nel Pannello di controllo, fare clic su **Aggiungi / Rimuovi programmi**.  
  
2.  Nel **Aggiungi / Rimuovi programmi** la finestra di dialogo, fare clic su **Installazione componenti di Windows**.  
  
3.  Nel **Aggiunta guidata componenti di Windows**, selezionare il **Internet Information Services (IIS)** casella di controllo e quindi fare clic su **Avanti**.  
  
4.  Se il **i file necessari** viene visualizzata la finestra di dialogo, inserire il disco di installazione sistema operativo, selezionare la cartella i386 e quindi fare clic su **OK**.  
  
5.  Al termine dell'installazione, fare clic su **fine**.  
  
6.  Chiudere il **Aggiungi / Rimuovi programmi** la finestra di dialogo e quindi chiudere **Pannello di controllo**.  
  
### <a name="to-verify-the-installation-of-iis-and-aspnet"></a>Per verificare l'installazione di IIS e ASP.NET  
  
1.  Salvare il file HTML trovato alla fine di questo argomento nella directory radice \InetPub\wwwroot e rinominarlo Default.aspx.  
  
2.  Aprire una finestra di browser.  
  
3.  Tipo `http://localhost/Default.aspx` nella casella Indirizzo e quindi premere INVIO.  
  
4.  Dovrebbe venire visualizzata una pagina Web contenente il testo "Hello World".  
  
> [!NOTE]
>  Ogni volta che si installa una nuova versione di [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)], è necessario registrare di nuovo aspnet_isapi come estensione del servizio Web per IIS. A tale scopo, eseguire il comando `aspnet_regiis –I –enable`.  
  
## <a name="sample-code"></a>Codice di esempio  
  
```xml  
<html>  
   <body>  
       <form >  
           <h3> Hello World  
           </h3>  
       </form>  
   </body>  
</html>  
```
