---
title: Uso di DataContractSerializer e DataContractResolver per fornire la funzionalità di NetDataContractSerializer
ms.date: 03/30/2017
ms.assetid: 1376658f-f695-45f7-a7e0-94664e9619ff
ms.openlocfilehash: 455ffe936373525f574d4401412c099d41d45f66
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59167219"
---
# <a name="using-datacontractserializer-and-datacontractresolver-to-provide-the-functionality-of-netdatacontractserializer"></a>Uso di DataContractSerializer e DataContractResolver per fornire la funzionalità di NetDataContractSerializer
Questo esempio dimostra come l'utilizzo di <xref:System.Runtime.Serialization.DataContractSerializer> con un <xref:System.Runtime.Serialization.DataContractResolver> appropriato offra la stessa funzionalità di <xref:System.Runtime.Serialization.NetDataContractSerializer>. Questo esempio mostra come creare il <xref:System.Runtime.Serialization.DataContractResolver> appropriato e come aggiungerlo a <xref:System.Runtime.Serialization.DataContractSerializer>.

## <a name="sample-details"></a>Dettagli dell'esempio
 <xref:System.Runtime.Serialization.NetDataContractSerializer> differisce da <xref:System.Runtime.Serialization.DataContractSerializer> un aspetto importante: <xref:System.Runtime.Serialization.NetDataContractSerializer> include informazioni sul tipo CLR nel XML serializzato, mentre <xref:System.Runtime.Serialization.DataContractSerializer> non esiste. Pertanto, la classe <xref:System.Runtime.Serialization.NetDataContractSerializer> può essere utilizzata solo se le estremità di serializzazione e deserializzazione condividono gli stessi tipi CLR. Si consiglia tuttavia di utilizzare la classe <xref:System.Runtime.Serialization.DataContractSerializer> perché le prestazioni sono migliori rispetto alla classe <xref:System.Runtime.Serialization.NetDataContractSerializer>. È possibile modificare le informazioni serializzate in <xref:System.Runtime.Serialization.DataContractSerializer> aggiungendo un <xref:System.Runtime.Serialization.DataContractResolver>.

 L'esempio è costituito da due progetti. Il primo progetto utilizza <xref:System.Runtime.Serialization.NetDataContractSerializer> per serializzare un oggetto. Il secondo progetto utilizza <xref:System.Runtime.Serialization.DataContractSerializer> con un <xref:System.Runtime.Serialization.DataContractResolver> per offrire la stessa funzionalità del primo progetto.

 Nell'esempio di codice seguente viene mostrata l'implementazione di un <xref:System.Runtime.Serialization.DataContractResolver> personalizzato, denominato `MyDataContractResolver`, aggiunto a <xref:System.Runtime.Serialization.DataContractSerializer> nel progetto DCSwithDCR.

```csharp
class MyDataContractResolver : DataContractResolver
{
    private XmlDictionary dictionary = new XmlDictionary();

    public MyDataContractResolver()
    {
    }

    // Used at deserialization
    // Allows users to map xsi:type name to any Type
    public override Type ResolveName(string typeName, string typeNamespace, DataContractResolver knownTypeResolver)
    {
        Type type = knownTypeResolver.ResolveName(typeName, typeNamespace, null);
        if (type == null)
        {
            type = Type.GetType(typeName + ", " + typeNamespace);
        }
        return type;
    }

    // Used at serialization
    // Maps any Type to a new xsi:type representation
    public override void ResolveType(Type dataContractType, DataContractResolver knownTypeResolver, out XmlDictionaryString typeName, out XmlDictionaryString typeNamespace)
    {
        knownTypeResolver.ResolveType(dataContractType, null, out typeName, out typeNamespace);
        if (typeName == null || typeNamespace == null)
        {
            XmlDictionary dictionary = new XmlDictionary();
            typeName = dictionary.Add(dataContractType.FullName);
            typeNamespace = dictionary.Add(dataContractType.Assembly.FullName);
        }
    }
}
```

#### <a name="to-use-this-sample"></a>Per usare questo esempio

1.  Usa Visual Studio 2012, aprire il file della soluzione Dcrsample.

2.  Fare clic sul file di soluzione e scegliere **proprietà**.

3.  Nel **pagine delle proprietà di soluzione** finestra di dialogo, sotto **proprietà comuni**, **progetto di avvio**, selezionare **più progetti di avvio:**.

4.  Accanto al **DCSwithDCR** progetto, selezionare **avviare** dal **azione** elenco a discesa.

5.  Accanto al **NetDCS** progetto, selezionare **avviare** dal **azione** elenco a discesa.

6.  Fare clic su **OK** per chiudere la finestra di dialogo.

7.  Per compilare la soluzione, premere CTRL+MAIUSC+B.

8.  Per eseguire la soluzione, premere CTRL+F5.

> [!IMPORTANT]
>  È possibile che gli esempi siano già installati nel computer. Verificare la directory seguente (impostazione predefinita) prima di continuare.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Se questa directory non esiste, andare al [Windows Communication Foundation (WCF) e gli esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti i Windows Communication Foundation (WCF) e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi. Questo esempio si trova nella directory seguente.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Contract\Data\NetDcSasDcSwithDCR`  
