---
title: Istruzioni per l'hosting su IIS (Internet Information Services)
ms.date: 03/30/2017
ms.assetid: 959a21c8-9d9d-4757-b255-4e57793ae9d6
ms.openlocfilehash: 226b47bfd90dc4cffb0a364a804016043cc25d02
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69929117"
---
# <a name="internet-information-service-hosting-instructions"></a>Istruzioni per l'hosting su IIS (Internet Information Services)
Per eseguire gli esempi ospitati su Internet Information Services (IIS) è necessario assicurarsi che IIS sia installato correttamente e sia in esecuzione.  
  
### <a name="to-install-iis-version-75-on-windows-server-2008-r2"></a>Installazione di IIS versione 7.5 in Windows Server 2008 R2  
  
1. In **Server Manager**selezionare **ruoli.** In **Riepilogo ruoli**fare clic su **Aggiungi ruoli**.  
  
2. Fare clic su **Avanti** per visualizzare la finestra di dialogo **Selezione ruoli server** .  
  
3. Selezionare **server applicazioni** dall'elenco **ruoli** , quindi fare clic due volte su **Avanti** per visualizzare la finestra di dialogo **Selezione servizi ruolo** per il ruolo server applicazioni.  
  
4. Selezionare la casella di controllo **server Web (IIS)** . Se viene richiesto di installare servizi ruolo e funzionalità aggiuntivi, fare clic su **Aggiungi funzionalità necessarie**. Fare clic due volte su **Avanti** per visualizzare la finestra di dialogo **Selezione servizi ruolo** per il ruolo server Web (IIS).  
  
5. Espandere **strumenti di gestione**, quindi espandere **compatibilità di gestione con IIS 6**. Selezionare **strumenti di script di IIS 6**. Se viene richiesto di installare servizi ruolo e funzionalità aggiuntivi, fare clic su **Aggiungi servizi ruolo necessari**. Fare clic su **Avanti**.  
  
6. Se il riepilogo delle selezioni è corretto, fare clic su **Installa**.  
  
7. Al termine dell'installazione, fare clic su **Chiudi**.  
  
### <a name="to-install-iis-version-75-on-windows-7"></a>Per installare IIS versione 7.5 in Windows 7  
  
1. Fare clic sul pulsante **Start**, quindi scegliere **Pannello di controllo**.  
  
2. Aprire il gruppo **programmi** .  
  
3. In **programmi e funzionalità**fare clic **su attivazione o disattivazione delle funzionalità Windows**.  
  
4. Viene visualizzata la finestra di dialogo **controllo dell'account utente** . Scegliere **Continua**.  
  
5. Verrà visualizzata la finestra di dialogo **funzionalità Windows** . Espandere l'elemento denominato **Internet Information Services**.  
  
6. Espandere l'elemento denominato **World Wide Web Services**.  
  
7. Espandere l'elemento funzionalità di **sviluppo dell'applicazione**.  
  
8. Verificare che gli elementi seguenti siano selezionati:  
  
    1. **Estendibilità .NET**  
  
    2. **ASP.NET 2.0**  
  
    3. **Estensioni ISAPI**  
  
    4. **Filtri ISAPI**  
  
9. Nell'elemento denominato **World Wide Web Services**espandere **funzionalità HTTP comuni**.  
  
10. Verificare che sia selezionato **contenuto statico** .  
  
11. Nell'elemento denominato **World Wide Web Services**espandere **sicurezza**.  
  
12. Assicurarsi che sia selezionata **l'opzione autenticazione di Windows** .  
  
13. Nella directory **Internet Information Services** espandere l'elemento **strumenti di gestione Web**, quindi selezionare **console di gestione IIS**.  
  
14. Espandere l'elemento compatibilità di **gestione con IIS 6**, quindi selezionare **strumenti di script di IIS 6**.  
  
15. Nella directory **Internet Information Services** espandere l'elemento con etichetta **Microsoft .NET Framework 3.5.1**, quindi selezionare **Windows Communication Foundation attivazione http**.  
  
16. Fare clic su **OK**.  
  
### <a name="to-install-iis-version-70-on-windows-server-2008"></a>Installazione di IIS versione 7.0 in Windows Server 2008  
  
1. In **Server Manager**selezionare **ruoli**. In **Riepilogo ruoli**fare clic su **Aggiungi ruoli**.  
  
2. Fare clic su **Avanti** per visualizzare la finestra di dialogo **Selezione ruoli server** .  
  
3. Selezionare **server applicazioni** dall'elenco **ruoli** , quindi fare clic due volte su **Avanti** per visualizzare la finestra di dialogo **Selezione servizi ruolo** per il ruolo server applicazioni.  
  
4. Selezionare la casella di controllo **server Web (IIS)** . Se viene richiesto di installare servizi ruolo e funzionalità aggiuntivi, fare clic su **Aggiungi funzionalità necessarie**. Fare clic due volte su **Avanti** per visualizzare la finestra di dialogo **Selezione servizi ruolo** per il ruolo server Web (IIS).  
  
5. Espandere **strumenti di gestione**, quindi espandere **compatibilità di gestione con IIS 6**. Selezionare **strumenti di script di IIS 6**. Se viene richiesto di installare servizi ruolo e funzionalità aggiuntivi, fare clic su **Aggiungi servizi ruolo necessari**. Fare clic su **Avanti**.  
  
6. Se il riepilogo delle selezioni è corretto, fare clic su **Installa**.  
  
7. Al termine dell'installazione, fare clic su **Chiudi**.  
  
### <a name="to-install-iis-version-70-on-windows-vista"></a>Per installare IIS sulla versione 7.0 in Windows Vista  
  
1. Fare clic sul pulsante Start, quindi scegliere Pannello di controllo.  
  
2. Selezionare il gruppo **programmi** .  
  
3. In **programmi e funzionalità**fare clic **su attivazione o disattivazione delle funzionalità Windows**.  
  
4. Viene visualizzata la finestra di dialogo **controllo dell'account utente** . Scegliere **Continua**.  
  
5. Verrà visualizzata la finestra di dialogo **funzionalità Windows** . Espandere l'elemento denominato **Internet Information Services**.  
  
6. Espandere l'elemento denominato **World Wide Web Services**.  
  
7. Espandere l'elemento funzionalità di **sviluppo dell'applicazione**.  
  
8. Verificare che gli elementi seguenti siano selezionati:  
  
    1. **Estendibilità .NET**  
  
    2. **ASP.NET 2.0**  
  
    3. **Estensioni ISAPI**  
  
    4. **Filtri ISAPI**  
  
9. Espandere l'elemento strumenti di **gestione Web**, quindi selezionare Console di **Gestione IIS**.  
  
10. Nell'elemento denominato **World Wide Web Services**espandere **funzionalità HTTP comuni**.  
  
11. Verificare che sia selezionato **contenuto statico** .  
  
12. Nell'elemento denominato **World Wide Web Services**espandere **sicurezza**.  
  
13. Assicurarsi che sia selezionata **l'autenticazione di Windows** .  
  
14. Espandere l'elemento compatibilità di **gestione con IIS 6**, quindi selezionare **strumenti di script di IIS 6**.  
  
15. Espandere l'elemento con etichetta **Microsoft .NET Framework 3,0**, quindi selezionare **Windows Communication Foundation attivazione http**.  
  
16. Fare clic su **OK**.  
  
### <a name="to-install-iis-version-60-on-windows-server-2003"></a>Per installare IIS versione 6.0 in Windows Server 2003  
  
1. In **Gestisci il server**fare clic su **Aggiungi o Rimuovi un ruolo**, quindi fare clic su **Avanti**.  
  
2. Selezionare **server applicazioni (IIS, ASP.NET)** nell'elenco **ruolo server** , quindi fare clic su **Avanti**.  
  
3. Selezionare la casella di controllo **abilita ASP.NET** , quindi fare clic su **Avanti**.  
  
4. Se il riepilogo delle selezioni è corretto, fare clic su Avanti.  
  
### <a name="to-install-iis-version-51-on-windows-xp-with-service-pack-2-and-service-pack-3-installed"></a>Per installare IIS versione 5.1 in Windows XP con Service Pack 2 e Service Pack 3 installati  
  
1. Nel pannello di controllo, fare clic su **Installazione applicazioni**.  
  
2. Nella finestra di dialogo **Installazione applicazioni** fare clic su **Aggiungi/Rimuovi componenti di Windows**.  
  
3. Nella **procedura guidata componenti di Windows**selezionare la casella di controllo **Internet Information Services (IIS)** , quindi fare clic su **Avanti**.  
  
4. Se viene visualizzata la finestra di dialogo **file necessari** , inserire il disco di installazione del sistema operativo, passare alla cartella i386, quindi fare clic su **OK**.  
  
5. Al termine dell'installazione, fare clic su **fine**.  
  
6. Chiudere la finestra di dialogo **Installazione applicazioni** e quindi chiudere il **Pannello di controllo**.  
  
### <a name="to-verify-the-installation-of-iis-and-aspnet"></a>Per verificare l'installazione di IIS e ASP.NET  
  
1. Salvare il file HTML trovato alla fine di questo argomento nella directory radice \InetPub\wwwroot e rinominarlo Default.aspx.  
  
2. Aprire una finestra di browser.  
  
3. Digitare `http://localhost/Default.aspx` nella casella Address, quindi premere INVIO.  
  
4. Dovrebbe venire visualizzata una pagina Web contenente il testo "Hello World".  
  
> [!NOTE]
> Ogni volta che si installa una nuova versione del .NET Framework, è necessario ripetere la registrazione di aspnet_isapi come estensione del servizio Web per IIS. A tale scopo, eseguire il comando `aspnet_regiis –I –enable`.  
  
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
