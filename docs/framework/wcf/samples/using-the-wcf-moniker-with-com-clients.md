---
title: Utilizzo del moniker WCF con i client COM
ms.date: 03/30/2017
ms.assetid: e2799bfe-88bd-49d7-9d6d-ac16a9b16b04
ms.openlocfilehash: 76b7697f431575e7bde83204739cb23f96d27064
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84596487"
---
# <a name="using-the-wcf-moniker-with-com-clients"></a>Utilizzo del moniker WCF con i client COM
In questo esempio viene illustrato come utilizzare il moniker del servizio Windows Communication Foundation (WCF) per integrare servizi Web in ambienti di sviluppo basati su COM, ad esempio Microsoft Office Visual Basic, Applications Edition (Office VBA) o Visual Basic 6,0. L'esempio è costituito da un client Windows Script Host (file con estensione vbs), una libreria di classi di supporto (file con estensione dll) e una libreria di servizi (file con estensione dll) ospitati in Internet Information Services (IIS). Il servizio è un servizio di calcolatrice e il client COM chiama operazioni matematiche, Add, Subtract, Multiply e Divide, nel servizio. L'attività del client è visibile nella finestra di messaggio.  
  
> [!NOTE]
> La procedura di installazione e le istruzioni di compilazione per questo esempio si trovano alla fine di questo argomento.  
  
> [!IMPORTANT]
> È possibile che gli esempi siano già installati nel computer. Verificare la directory seguente (impostazione predefinita) prima di continuare.  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> Se questa directory non esiste, passare a [Windows Communication Foundation (WCF) ed esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) per scaricare tutti i Windows Communication Foundation (WCF) ed [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi. Questo esempio si trova nella directory seguente.  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\Interop\COM`  
  
 Il servizio implementa un contratto `ICalculator` definito nel modo illustrato nel codice di esempio seguente.  
  
```csharp
[ServiceContract(Namespace="http://Microsoft.ServiceModel.Samples")]  
public interface ICalculator  
{  
    [OperationContract]  
    double Add(double n1, double n2);  
    [OperationContract]  
    double Subtract(double n1, double n2);  
    [OperationContract]  
    double Multiply(double n1, double n2);  
    [OperationContract]  
    double Divide(double n1, double n2);  
}  
```  
  
 Nell'esempio vengono descritti tre approcci alternativi per l'uso del moniker:  
  
- Contratto tipizzato: il contratto viene registrato come tipo visibile a COM sul computer client.  
  
- Contratto WSDL: il contratto viene fornito sotto forma di documento WSDL.  
  
- Contratto MEX: il contratto viene recuperato in fase di esecuzione da un endpoint di scambio di metadati (MEX).  
  
## <a name="typed-contract"></a>Contratto tipizzato  
 Per usare il moniker con un uso del contratto tipizzato, è necessario registrare con COM i tipi per il contratto di servizio forniti degli attribuiti appropriati. Per prima cosa, è necessario generare un client usando lo [strumento ServiceModel Metadata Utility Tool (Svcutil. exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md). Eseguire il comando seguente da un prompt dei comandi nella directory del client per generare il proxy tipizzato.  
  
```console  
svcutil.exe /n:http://Microsoft.ServiceModel.Samples,Microsoft.ServiceModel.Samples http://localhost/servicemodelsamples/service.svc /out:generatedClient.cs  
```  
  
 Questa classe deve essere inclusa in un progetto e il progetto deve essere configurato per generare un assembly visibile a COM e firmato durante la compilazione. Nel file AssemblyInfo.cs deve essere incluso l'attributo seguente:  
  
```csharp
[assembly: ComVisible(true)]  
```  
  
 Dopo aver compilato il progetto, registrare i tipi visibili a COM usando `regasm`, come illustrato nell'esempio seguente:  
  
```console  
regasm.exe /tlb:CalcProxy.tlb client.dll  
```  
  
 L'assembly creato deve essere aggiunto alla Global Assembly Cache. Sebbene non sia strettamente obbligatoria, questa operazione semplifica il processo in cui la fase di esecuzione individua l'assembly. Il comando seguente aggiunge l'assembly alla Global Assembly Cache.  
  
```console  
gacutil.exe /i client.dll  
```  
  
> [!NOTE]
> Il moniker del servizio richiede solo la registrazione del tipo e non usa il proxy per comunicare con il servizio.  
  
 L'applicazione client ComCalcClient.vbs usa la funzione `GetObject` per costruire un proxy per il servizio, usando la sintassi del moniker del servizio per specificare l'indirizzo, l'associazione e contratto per il servizio.  
  
```vbscript
Set typedServiceMoniker = GetObject(  
"service4:address=http://localhost/ServiceModelSamples/service.svc, binding=wsHttpBinding,
contractType={9213C6D2-5A6F-3D26-839B-3BA9B82228D3}")  
```  
  
 I parametri usati dal moniker specificano:  
  
- L'indirizzo dell'endpoint del servizio.  
  
- L'associazione che il client dovrebbe usare per connettersi a quell'endpoint. In questo caso, il wsHttpBinding definito dal sistema viene usato anche se le associazioni personalizzate possono essere definite nei file di configurazione del client. Per l'uso con Windows Script Host, l'associazione personalizzata viene definita in un file Cscript.exe.config nella stessa directory di Cscript.exe.  
  
- Il tipo del contratto è supportato sull'endpoint. Questo è il tipo generato e registrato in precedenza. Poiché Visual Basic script non fornisce un ambiente COM fortemente tipizzato, è necessario specificare un identificatore per il contratto. Questo GUID è l'`interfaceID` da CalcProxy.tlb e può essere visualizzato usando gli strumenti COM, ad esempio il Visualizzatore oggetti OLE/COM (OleView.exe). Per ambienti fortemente tipizzati, ad esempio Office VBA o Visual Basic 6,0, è possibile aggiungere un riferimento esplicito alla libreria dei tipi e quindi dichiarare il tipo dell'oggetto proxy al posto del parametro Contract. In questo modo si fornisce anche supporto IntelliSense durante lo sviluppo dell'applicazione client.  
  
 Una volta costruita l'istanza del proxy con il moniker del servizio, l'applicazione client può chiamare i metodi sul proxy e l'infrastruttura del moniker del servizio può chiamare le operazioni del servizio corrispondenti:  
  
```vbscript  
' Call the service operations using the moniker object  
WScript.Echo "Typed service moniker: 100 + 15.99 = " & typedServiceMoniker.Add(100, 15.99)  
```  
  
 Quando si esegue l'esempio, la risposta dell'operazione viene visualizzata in una finestra di messaggio di Windows Script Host. Viene illustrato un client COM che esegue chiamate COM usando il moniker tipizzato per comunicare con un servizio WCF. Nonostante si usi COM nell'applicazione client, la comunicazione con il servizio è costituita solo da chiamate del servizio Web.  
  
## <a name="wsdl-contract"></a>Contratto WSDL  
 Per usare il moniker con un contratto WSDL non è richiesta alcuna registrazione della libreria client, ma il contratto WSDL per il servizio deve essere recuperato tramite un meccanismo fuori banda, ad esempio usando un browser per accedere all'endpoint WSDL per il servizio. Il moniker può accedere quindi a quel contratto in fase di esecuzione.  
  
 L'applicazione client ComCalcClient.vbs usa `FileSystemObject` per accedere al file WSDL salvato sul computer locale, quindi usa la funzione `GetObject` per costruire un proxy per il servizio:  
  
```vbscript  
' Open the WSDL contract file and read it all into the wsdlContract string  
Const ForReading = 1  
Set objFSO = CreateObject("Scripting.FileSystemObject")  
Set objFile = objFSO.OpenTextFile("serviceWsdl.xml", ForReading)  
wsdlContract = objFile.ReadAll  
objFile.Close  
  
' Create a string for the service moniker including the content of the WSDL contract file  
wsdlMonikerString = "service4:address='http://localhost/ServiceModelSamples/service.svc'"  
wsdlMonikerString = wsdlMonikerString + ", binding=WSHttpBinding_ICalculator, bindingNamespace='http://Microsoft.ServiceModel.Samples'"  
wsdlMonikerString = wsdlMonikerString + ", wsdl='" & wsdlContract & "'"  
wsdlMonikerString = wsdlMonikerString + ", contract=ICalculator, contractNamespace='http://Microsoft.ServiceModel.Samples'"  
  
' Create the service moniker object  
Set wsdlServiceMoniker = GetObject(wsdlMonikerString)  
```  
  
 I parametri usati dal moniker specificano:  
  
- L'indirizzo dell'endpoint del servizio.  
  
- L'associazione che il client deve usare per connettersi con quell'endpoint e lo spazio dei nomi nel quale viene definita quell'associazione. In questo caso, viene usata `wsHttpBinding_ICalculator`.  
  
- Il WSDL che definisce il contratto. In questo caso è la stringa letta dal file serviceWsdl.xml.  
  
- Il nome e lo spazio dei nomi del contratto. Questa identificazione è richiesta perché il WSDL potrebbe contenere più di un contratto.  
  
    > [!NOTE]
    > Per impostazione predefinita, i servizi WCF generano file WSDL distinti per ogni spazio dei nomi utilizzato da. Questi vengono collegati usando il costrutto di importazione di WSDL. Poiché il moniker si aspetta una sola definizione WSDL, il servizio deve usare un solo spazio dei nomi, come illustrato in questo esempio, o i file separati devono essere uniti manualmente.  
  
 Una volta costruita l'istanza del proxy con il moniker del servizio, l'applicazione client può chiamare i metodi sul proxy e l'infrastruttura del moniker del servizio può chiamare le operazioni del servizio corrispondenti:  
  
```vbscript  
' Call the service operations using the moniker object  
WScript.Echo "WSDL service moniker: 145 - 76.54 = " & wsdlServiceMoniker.Subtract(145, 76.54)  
```  
  
 Quando si esegue l'esempio, la risposta dell'operazione viene visualizzata in una finestra di messaggio di Windows Script Host. Viene illustrato un client COM che esegue chiamate COM usando il moniker con un contratto WSDL per comunicare con un servizio WCF.  
  
## <a name="metadata-exchange-contract"></a>Contratto di scambio di metadati  
 Per usare il moniker con un contratto MEX, come per il contratto WSDL, non è richiesta alcuna registrazione client. Il contratto per il servizio viene recuperato in fase di esecuzione usando lo scambio di metadati interno.  
  
 L'applicazione client ComCalcClient.vbs usa quindi la funzione `GetObject` per costruire un proxy per il servizio.  
  
```vbscript  
' Create a string for the service moniker specifying the address to retrieve the service metadata from  
mexMonikerString = "service4:mexAddress='http://localhost/servicemodelsamples/service.svc/mex'"  
mexMonikerString = mexMonikerString + ", address='http://localhost/ServiceModelSamples/service.svc'"  
mexMonikerString = mexMonikerString + ", binding=WSHttpBinding_ICalculator, bindingNamespace='http://Microsoft.ServiceModel.Samples'"  
mexMonikerString = mexMonikerString + ", contract=ICalculator, contractNamespace='http://Microsoft.ServiceModel.Samples'"  
  
' Create the service moniker object  
Set mexServiceMoniker = GetObject(mexMonikerString)  
```  
  
 I parametri usati dal moniker specificano:  
  
- L'indirizzo dell'endpoint di scambio di metadati del servizio.  
  
- L'indirizzo dell'endpoint del servizio.  
  
- L'associazione che il client deve usare per connettersi con quell'endpoint e lo spazio dei nomi nel quale viene definita quell'associazione. In questo caso, viene usata `wsHttpBinding_ICalculator`.  
  
- Il nome e lo spazio dei nomi del contratto. Questa identificazione è richiesta perché il WSDL potrebbe contenere più di un contratto.  
  
 Una volta costruita l'istanza del proxy con il moniker del servizio, l'applicazione client può chiamare i metodi sul proxy e l'infrastruttura del moniker del servizio può chiamare le operazioni del servizio corrispondenti:  
  
```vbscript  
' Call the service operations using the moniker object  
WScript.Echo "MEX service moniker: 9 * 81.25 = " & mexServiceMoniker.Multiply(9, 81.25)  
```  
  
 Quando si esegue l'esempio, la risposta dell'operazione viene visualizzata in una finestra di messaggio di Windows Script Host. Viene illustrato un client COM che esegue chiamate COM usando il moniker con un contratto MEX per comunicare con un servizio WCF.  
  
#### <a name="to-set-up-and-build-the-sample"></a>Per impostare e compilare l'esempio  
  
1. Assicurarsi di avere eseguito la [procedura di installazione singola per gli esempi di Windows Communication Foundation](one-time-setup-procedure-for-the-wcf-samples.md).  
  
2. Per compilare l'edizione in C# o Visual Basic .NET della soluzione, seguire le istruzioni in [Building the Windows Communication Foundation Samples](building-the-samples.md).  
  
3. Da un Prompt dei comandi per gli sviluppatori per Visual Studio, aprire la cartella \client\bin\ nella cartella specifica del linguaggio.  
  
    > [!NOTE]
    > Se si utilizza Windows Vista, Windows Server 2008, Windows 7 o Windows Server 2008 R2, assicurarsi di eseguire il prompt dei comandi con privilegi di amministratore.  
  
4. Digitare `tlbexp.exe client.dll /out:CalcProxy.tlb` per esportare la dll in un file tlb. È previsto un "Avviso dell'utilità di esportazione della libreria dei tipi", ma ciò non rappresenta un problema, perché il tipo generico non è obbligatorio.  
  
5. Digitare `regasm.exe /tlb:CalcProxy.tlb client.dll` per registrare i tipi con com. È previsto un "Avviso dell'utilità di esportazione della libreria dei tipi", ma ciò non rappresenta un problema, perché il tipo generico non è obbligatorio.  
  
6. Digitare `gacutil.exe /i client.dll` per aggiungere l'assembly alla Global assembly cache.  
  
#### <a name="to-run-the-sample-on-the-same-computer"></a>Per eseguire l'esempio nello stesso computer  
  
1. Verificare che sia possibile accedere al servizio utilizzando un browser digitando l'indirizzo seguente: `http://localhost/servicemodelsamples/service.svc` . In risposta, viene visualizzata un pagina di conferma.  
  
2. Eseguire ComCalcClient.vbs da \client, nella cartella specifica della lingua. L'attività del client viene visualizzata nella finestra di messaggio.  
  
3. Se il client e il servizio non sono in grado di comunicare, vedere [Suggerimenti per la risoluzione dei problemi per gli esempi di WCF](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).  
  
#### <a name="to-run-the-sample-across-computers"></a>Per eseguire l'esempio tra più computer  
  
1. Sul computer del servizio creare una directory virtuale denominata ServiceModelSamples. Lo script Setupvroot.bat incluso nell'esempio può essere usato per creare la directory del disco e quella virtuale.  
  
2. Copiare i file del programma del servizio da %SystemDrive%\Inetpub\wwwroot\servicemodelsamples nella directory virtuale di ServiceModelSamples nel computer del servizio. Verificare di includere i file nella directory \bin.  
  
3. Copiare il file script del client dalla cartella \client, nella cartella specifica della lingua, ne computer client.  
  
4. Nel file script modificare il valore dell'indirizzo della definizione dell'endpoint affinché corrisponda al nuovo indirizzo del servizio. Nell'indirizzo sostituire qualsiasi riferimento a "localhost" con un nome di dominio completo.  
  
5. Copiare il file WSDL nel computer client. Nel file WSDL, serviceWsdl.xml, sostituire qualsiasi riferimento a "localhost" con un nome di dominio completo nell'indirizzo.  
  
6. Copiare la libreria Client.dll dalla cartella \client\bin\, nella cartella specifica della lingua, a una directory sul computer client.  
  
7. Da un prompt dei comandi spostarsi a tale directory di destinazione sul computer client. Se si utilizza Windows Vista o Windows Server 2008, assicurarsi di eseguire il prompt dei comandi come amministratore.  
  
8. Digitare `tlbexp.exe client.dll /out:CalcProxy.tlb` per esportare la dll in un file tlb. È previsto un "Avviso dell'utilità di esportazione della libreria dei tipi", ma ciò non rappresenta un problema, perché il tipo generico non è obbligatorio.  
  
9. Digitare `regasm.exe /tlb:CalcProxy.tlb client.dll` per registrare i tipi con com. Verificare che il percorso sia stato impostato sulla cartella che contiene `regasm.exe` prima di eseguire il comando.  
  
10. Digitare `gacutil.exe /i client.dll` per aggiungere l'assembly alla Global assembly cache. Verificare che il percorso sia stato impostato sulla cartella che contiene `gacutil.exe` prima di eseguire il comando.  
  
11. Verificare che sia possibile accedere al servizio dal computer client usando un browser.  
  
12. Sul computer client avviare ComCalcClient.vbs.  
  
#### <a name="to-clean-up-after-the-sample"></a>Per eseguire la pulizia dopo l'esempio  
  
- Per motivi di sicurezza, rimuovere la definizione della directory virtuale e le autorizzazioni concesse durante l'installazione quando si è finito di lavorare con gli esempi eseguendo il file batch denominato Cleanupvroot.bat.  
