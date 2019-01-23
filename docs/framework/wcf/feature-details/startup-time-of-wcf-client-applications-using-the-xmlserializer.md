---
title: "Procedura: Migliorare l'avvio tempo di applicazioni Client WCF usando XmlSerializer"
ms.date: 03/30/2017
ms.assetid: 21093451-0bc3-4b1a-9a9d-05f7f71fa7d0
ms.openlocfilehash: fb98919fe6d0ec67e5fea8c483e4993f2632267f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54503131"
---
# <a name="how-to-improve-the-startup-time-of-wcf-client-applications-using-the-xmlserializer"></a>Procedura: Migliorare l'avvio tempo di applicazioni Client WCF usando XmlSerializer
I servizi e le applicazioni client che utilizzano tipi di dati serializzabili tramite <xref:System.Xml.Serialization.XmlSerializer> generano e compilano il codice di serializzazione per tali dati in fase di esecuzione, il che può rallentare le prestazioni all'avvio.  
  
> [!NOTE]
>  Un codice di serializzazione pregenerato può essere utilizzato solamente nelle applicazioni client e non nei servizi.  
  
 Il [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) può migliorare le prestazioni di avvio per queste applicazioni generando il codice di serializzazione necessario dagli assembly compilati per l'applicazione. Svcutil.exe genera codice di serializzazione per tutti i tipi di dati utilizzati nei contratti di servizio nell'assembly dell'applicazione compilata che può essere serializzato utilizzando <xref:System.Xml.Serialization.XmlSerializer>. I contratti del servizio e dell'operazione che utilizzano <xref:System.Xml.Serialization.XmlSerializer> sono contrassegnati con <xref:System.ServiceModel.XmlSerializerFormatAttribute>.  
  
### <a name="to-generate-xmlserializer-serialization-code"></a>Per generare il codice di serializzazione XmlSerializer  
  
1.  Compilare il codice del servizio o del client in uno o più assembly.  
  
2.  Aprire un prompt dei comandi SDK.  
  
3.  Al prompt dei comandi, avviare lo strumento Svcutil.exe usando il formato seguente.  
  
    ```  
    svcutil.exe /t:xmlSerializer  <assemblyPath>*  
    ```  
  
     L'argomento `assemblyPath` specifica il percorso di un assembly che contiene tipi di contratto di servizio. Svcutil.exe genera codice di serializzazione per tutti i tipi di dati utilizzati nei contratti di servizio nell'assembly dell'applicazione compilata che può essere serializzato utilizzando <xref:System.Xml.Serialization.XmlSerializer>.  
  
     Svcutil.exe può generare solo codice di serializzazione C#. Viene generato un file di codice sorgente per ogni assembly di input. Non è possibile usare la **/language** switch per modificare la lingua del codice generato.  
  
     Per specificare il percorso agli assembly dipendenti, usare il **/Reference** opzione.  
  
4.  Rendere il codice di serializzazione generato disponibile all'applicazione utilizzando una delle opzioni seguenti:  
  
    1.  Compilare il codice di serializzazione generato in un assembly separato con il nome [*assembly originale*]. XmlSerializers. dll (ad esempio, XmlSerializers). L'applicazione deve essere in grado di caricare l'assembly che deve essere firmato con la stessa chiave dell'assembly originale. Se si ricompila l'assembly originale, è necessario rigenerare l'assembly di serializzazione.  
  
    2.  Compilare il codice di serializzazione generato in un assembly separato e utilizzare <xref:System.Xml.Serialization.XmlSerializerAssemblyAttribute> sul contratto di servizio che utilizza <xref:System.ServiceModel.XmlSerializerFormatAttribute>. Impostare le proprietà <xref:System.Xml.Serialization.XmlSerializerAssemblyAttribute.AssemblyName%2A> o <xref:System.Xml.Serialization.XmlSerializerAssemblyAttribute.CodeBase%2A> per puntare all'assembly di serializzazione compilato.  
  
    3.  Compilare il codice di serializzazione generato nell'assembly dell'applicazione e aggiungere <xref:System.Xml.Serialization.XmlSerializerAssemblyAttribute> al contratto di servizio che utilizza <xref:System.ServiceModel.XmlSerializerFormatAttribute>. Non impostare le proprietà <xref:System.Xml.Serialization.XmlSerializerAssemblyAttribute.AssemblyName%2A> o <xref:System.Xml.Serialization.XmlSerializerAssemblyAttribute.CodeBase%2A>. L'assembly corrente viene considerato automaticamente l'assembly di serializzazione predefinito.  
  
### <a name="to-generate-xmlserializer-serialization-code-in-visual-studio"></a>Per generare il codice di serializzazione XmlSerializer in Visual Studio  
  
1.  Creare il servizio WCF e il client progetti in Visual Studio. Quindi, aggiungere un riferimento al servizio nel progetto client.  
  
2.  Aggiungere un <xref:System.ServiceModel.XmlSerializerFormatAttribute> al contratto di servizio nel *reference.cs* file nel progetto dell'app client sotto **serviceReference** -> **svcmap** . Si noti che è necessario visualizzare tutti i file in **Esplora soluzioni** per visualizzare questi file.  
  
3.  Compilare l'app client.  
  
4.  Usare la [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) per creare un serializzatore pregenerato *cs* file usando il comando:  
  
    ```  
    svcutil.exe /t:xmlSerializer  <assemblyPath>*  
    ```  
  
     L'argomento assemblyPath specifica il percorso dell'assembly client WCF.  
  
     Ad esempio:  
  
    ```  
    svcutil.exe /t:xmlSerializer wcfclient.exe  
    ```  
  
     Il *WCFClient.XmlSerializers.dll.cs* verrà generati file.  
  
5.  Compilare l'assembly di serializzazione generato in precedenza.  
  
     In base all'esempio nel passaggio precedente, il comando di compilazione sarà il seguente:  
  
    ```  
    csc /r:wcfclient.exe /out:WCFClient.XmlSerializers.dll /t:library WCFClient.XmlSerializers.dll.cs  
    ```  
  
     Assicurarsi che il generato *WCFClient.XmlSerializers.dll* è nella stessa directory dell'App client, ovvero *WCFClient.exe* in questo caso.  
  
6.  Eseguire l'app client come di consueto. Verrà utilizzato l'assembly di serializzazione generato in precedenza.  
  
## <a name="example"></a>Esempio  
 Nel comando seguente vengono generati i tipi di serializzazione per i tipi `XmlSerializer` utilizzati da qualsiasi contratto di servizio nell'assembly.  
  
```  
svcutil /t:xmlserializer myContractLibrary.exe  
```  
  
## <a name="see-also"></a>Vedere anche
- [Strumento ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)
