---
title: 'Procedura: migliorare il tempo di avvio di applicazioni client WCF usando XmlSerializer'
ms.date: 03/30/2017
ms.assetid: 21093451-0bc3-4b1a-9a9d-05f7f71fa7d0
ms.openlocfilehash: 6f61c57998cfc21b66f278a1a2381407ec2c39ce
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33500129"
---
# <a name="how-to-improve-the-startup-time-of-wcf-client-applications-using-the-xmlserializer"></a>Procedura: migliorare il tempo di avvio di applicazioni client WCF usando XmlSerializer
I servizi e le applicazioni client che utilizzano tipi di dati serializzabili tramite <xref:System.Xml.Serialization.XmlSerializer> generano e compilano il codice di serializzazione per tali dati in fase di esecuzione, il che può rallentare le prestazioni all'avvio.  
  
> [!NOTE]
>  Un codice di serializzazione pregenerato può essere utilizzato solamente nelle applicazioni client e non nei servizi.  
  
 Il [strumento ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) può migliorare le prestazioni di avvio per queste applicazioni per la generazione del codice di serializzazione necessari dagli assembly compilati per l'applicazione. Svcutil.exe genera codice di serializzazione per tutti i tipi di dati utilizzati nei contratti di servizio nell'assembly dell'applicazione compilata che può essere serializzato utilizzando <xref:System.Xml.Serialization.XmlSerializer>. I contratti del servizio e dell'operazione che utilizzano <xref:System.Xml.Serialization.XmlSerializer> sono contrassegnati con <xref:System.ServiceModel.XmlSerializerFormatAttribute>.  
  
### <a name="to-generate-xmlserializer-serialization-code"></a>Per generare il codice di serializzazione XmlSerializer  
  
1.  Compilare il codice del servizio o del client in uno o più assembly.  
  
2.  Aprire un prompt dei comandi SDK.  
  
3.  Al prompt dei comandi, avviare lo strumento Svcutil.exe usando il formato seguente.  
  
    ```  
    svcutil.exe /t:xmlSerializer  <assemblyPath>*  
    ```  
  
     L'argomento `assemblyPath` specifica il percorso di un assembly che contiene tipi di contratto di servizio. Svcutil.exe genera codice di serializzazione per tutti i tipi di dati utilizzati nei contratti di servizio nell'assembly dell'applicazione compilata che può essere serializzato utilizzando <xref:System.Xml.Serialization.XmlSerializer>.  
  
     Svcutil.exe può generare solo codice di serializzazione C#. Viene generato un file di codice sorgente per ogni assembly di input. Non è possibile utilizzare il **/language** commutatore per modificare la lingua del codice generato.  
  
     Per specificare il percorso degli assembly dipendenti, utilizzare il **/Reference** opzione.  
  
4.  Rendere il codice di serializzazione generato disponibile all'applicazione utilizzando una delle opzioni seguenti:  
  
    1.  Compilare il codice di serializzazione generato in un assembly separato con il nome [*assembly originale*]. XmlSerializers. dll (ad esempio, MyApp.XmlSerializers.dll). L'applicazione deve essere in grado di caricare l'assembly che deve essere firmato con la stessa chiave dell'assembly originale. Se si ricompila l'assembly originale, è necessario rigenerare l'assembly di serializzazione.  
  
    2.  Compilare il codice di serializzazione generato in un assembly separato e utilizzare <xref:System.Xml.Serialization.XmlSerializerAssemblyAttribute> sul contratto di servizio che utilizza <xref:System.ServiceModel.XmlSerializerFormatAttribute>. Impostare le proprietà <xref:System.Xml.Serialization.XmlSerializerAssemblyAttribute.AssemblyName%2A> o <xref:System.Xml.Serialization.XmlSerializerAssemblyAttribute.CodeBase%2A> per puntare all'assembly di serializzazione compilato.  
  
    3.  Compilare il codice di serializzazione generato nell'assembly dell'applicazione e aggiungere <xref:System.Xml.Serialization.XmlSerializerAssemblyAttribute> al contratto di servizio che utilizza <xref:System.ServiceModel.XmlSerializerFormatAttribute>. Non impostare le proprietà <xref:System.Xml.Serialization.XmlSerializerAssemblyAttribute.AssemblyName%2A> o <xref:System.Xml.Serialization.XmlSerializerAssemblyAttribute.CodeBase%2A>. L'assembly corrente viene considerato automaticamente l'assembly di serializzazione predefinito.  
  
### <a name="to-generate-xmlserializer-serialization-code-in-visual-studio"></a>Per generare il codice di serializzazione XmlSerializer in Visual Studio  
  
1.  Creare il servizio WCF e il client progetti in Visual Studio. Quindi, aggiungere un riferimento al progetto client.  
  
2.  Aggiungere un <xref:System.ServiceModel.XmlSerializerFormatAttribute> al contratto di servizio nel *reference.cs* file nel progetto dell'app client in **serviceReference** -> **svcmap** . Si noti che è necessario visualizzare tutti i file **Esplora** per visualizzare questi file.  
  
3.  Compilare l'applicazione client.  
  
4.  Utilizzare il [strumento ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) per creare un serializzatore pregenerato *cs* file utilizzando il comando:  
  
    ```  
    svcutil.exe /t:xmlSerializer  <assemblyPath>*  
    ```  
  
     L'argomento assemblyPath specifica il percorso dell'assembly client WCF.  
  
     Ad esempio:  
  
    ```  
    svcutil.exe /t:xmlSerializer wcfclient.exe  
    ```  
  
     Il *WCFClient.XmlSerializers.dll.cs* file verrà generato.  
  
5.  Compilare l'assembly di serializzazione generati in precedenza.  
  
     In base all'esempio nel passaggio precedente, il comando di compilazione potrebbe essere la seguente:  
  
    ```  
    csc /r:wcfclient.exe /out:WCFClient.XmlSerializers.dll /t:library WCFClient.XmlSerializers.dll.cs  
    ```  
  
     Verificare che il generato *WCFClient.XmlSerializers.dll* è nella stessa directory dell'applicazione client, ovvero *WCFClient.exe* in questo caso.  
  
6.  Eseguire l'app client come di consueto. Verrà utilizzato l'assembly di serializzazione generati in precedenza.  
  
## <a name="example"></a>Esempio  
 Nel comando seguente vengono generati i tipi di serializzazione per i tipi `XmlSerializer` utilizzati da qualsiasi contratto di servizio nell'assembly.  
  
```  
svcutil /t:xmlserializer myContractLibrary.exe  
```  
  
## <a name="see-also"></a>Vedere anche  
 [Strumento ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)
