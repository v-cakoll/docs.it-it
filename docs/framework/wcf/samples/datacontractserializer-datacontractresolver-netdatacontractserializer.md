---
title: Uso di DataContractSerializer e DataContractResolver per fornire la funzionalità di NetDataContractSerializer
ms.date: 03/30/2017
ms.assetid: 1376658f-f695-45f7-a7e0-94664e9619ff
ms.openlocfilehash: 0378f8d6e21f44eb1f39e9ebf51ef0dfaf8d8e8a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61990405"
---
# <a name="using-datacontractserializer-and-datacontractresolver-to-provide-the-functionality-of-netdatacontractserializer"></a><span data-ttu-id="d5b13-102">Uso di DataContractSerializer e DataContractResolver per fornire la funzionalità di NetDataContractSerializer</span><span class="sxs-lookup"><span data-stu-id="d5b13-102">Using DataContractSerializer and DataContractResolver to Provide the Functionality of NetDataContractSerializer</span></span>
<span data-ttu-id="d5b13-103">Questo esempio dimostra come l'utilizzo di <xref:System.Runtime.Serialization.DataContractSerializer> con un <xref:System.Runtime.Serialization.DataContractResolver> appropriato offra la stessa funzionalità di <xref:System.Runtime.Serialization.NetDataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="d5b13-103">This sample demonstrates how the use of <xref:System.Runtime.Serialization.DataContractSerializer> with an appropriate <xref:System.Runtime.Serialization.DataContractResolver> provides the same functionality as <xref:System.Runtime.Serialization.NetDataContractSerializer>.</span></span> <span data-ttu-id="d5b13-104">Questo esempio mostra come creare il <xref:System.Runtime.Serialization.DataContractResolver> appropriato e come aggiungerlo a <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="d5b13-104">This sample shows how to create the appropriate <xref:System.Runtime.Serialization.DataContractResolver> and how to add it to the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>

## <a name="sample-details"></a><span data-ttu-id="d5b13-105">Dettagli dell'esempio</span><span class="sxs-lookup"><span data-stu-id="d5b13-105">Sample details</span></span>
 <span data-ttu-id="d5b13-106">Le classi <xref:System.Runtime.Serialization.NetDataContractSerializer> e <xref:System.Runtime.Serialization.DataContractSerializer> differiscono per un aspetto importante: la classe <xref:System.Runtime.Serialization.NetDataContractSerializer> include informazioni di tipo CLR nell'XML serializzato, a differenza della classe <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="d5b13-106"><xref:System.Runtime.Serialization.NetDataContractSerializer> differs from <xref:System.Runtime.Serialization.DataContractSerializer> in one important way: <xref:System.Runtime.Serialization.NetDataContractSerializer> includes CLR type information in the serialized XML, whereas <xref:System.Runtime.Serialization.DataContractSerializer> does not.</span></span> <span data-ttu-id="d5b13-107">Pertanto, la classe <xref:System.Runtime.Serialization.NetDataContractSerializer> può essere utilizzata solo se le estremità di serializzazione e deserializzazione condividono gli stessi tipi CLR.</span><span class="sxs-lookup"><span data-stu-id="d5b13-107">Therefore, <xref:System.Runtime.Serialization.NetDataContractSerializer> can be used only if both the serializing and deserializing ends share the same CLR types.</span></span> <span data-ttu-id="d5b13-108">Si consiglia tuttavia di utilizzare la classe <xref:System.Runtime.Serialization.DataContractSerializer> perché le prestazioni sono migliori rispetto alla classe <xref:System.Runtime.Serialization.NetDataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="d5b13-108">However, it is recommended to use <xref:System.Runtime.Serialization.DataContractSerializer> because its performance is better than <xref:System.Runtime.Serialization.NetDataContractSerializer>.</span></span> <span data-ttu-id="d5b13-109">È possibile modificare le informazioni serializzate in <xref:System.Runtime.Serialization.DataContractSerializer> aggiungendo un <xref:System.Runtime.Serialization.DataContractResolver>.</span><span class="sxs-lookup"><span data-stu-id="d5b13-109">You can change the information that is serialized in <xref:System.Runtime.Serialization.DataContractSerializer> by adding a <xref:System.Runtime.Serialization.DataContractResolver> to it.</span></span>

 <span data-ttu-id="d5b13-110">L'esempio è costituito da due progetti.</span><span class="sxs-lookup"><span data-stu-id="d5b13-110">This sample consists of two projects.</span></span> <span data-ttu-id="d5b13-111">Il primo progetto utilizza <xref:System.Runtime.Serialization.NetDataContractSerializer> per serializzare un oggetto.</span><span class="sxs-lookup"><span data-stu-id="d5b13-111">The first project uses <xref:System.Runtime.Serialization.NetDataContractSerializer> to serialize an object.</span></span> <span data-ttu-id="d5b13-112">Il secondo progetto utilizza <xref:System.Runtime.Serialization.DataContractSerializer> con un <xref:System.Runtime.Serialization.DataContractResolver> per offrire la stessa funzionalità del primo progetto.</span><span class="sxs-lookup"><span data-stu-id="d5b13-112">The second project uses <xref:System.Runtime.Serialization.DataContractSerializer> with a <xref:System.Runtime.Serialization.DataContractResolver> to provide the same functionality as the first project.</span></span>

 <span data-ttu-id="d5b13-113">Nell'esempio di codice seguente viene mostrata l'implementazione di un <xref:System.Runtime.Serialization.DataContractResolver> personalizzato, denominato `MyDataContractResolver`, aggiunto a <xref:System.Runtime.Serialization.DataContractSerializer> nel progetto DCSwithDCR.</span><span class="sxs-lookup"><span data-stu-id="d5b13-113">The following code example shows the implementation of a custom <xref:System.Runtime.Serialization.DataContractResolver> named `MyDataContractResolver` that is added to the <xref:System.Runtime.Serialization.DataContractSerializer> in the DCSwithDCR project.</span></span>

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

#### <a name="to-use-this-sample"></a><span data-ttu-id="d5b13-114">Per usare questo esempio</span><span class="sxs-lookup"><span data-stu-id="d5b13-114">To use this sample</span></span>

1. <span data-ttu-id="d5b13-115">Usa Visual Studio 2012, aprire il file della soluzione Dcrsample.</span><span class="sxs-lookup"><span data-stu-id="d5b13-115">Using Visual Studio 2012, open the DCRSample.sln solution file.</span></span>

2. <span data-ttu-id="d5b13-116">Fare clic sul file di soluzione e scegliere **proprietà**.</span><span class="sxs-lookup"><span data-stu-id="d5b13-116">Right-click the solution file and choose **Properties**.</span></span>

3. <span data-ttu-id="d5b13-117">Nel **pagine delle proprietà di soluzione** finestra di dialogo, sotto **proprietà comuni**, **progetto di avvio**, selezionare **più progetti di avvio:**.</span><span class="sxs-lookup"><span data-stu-id="d5b13-117">In the **Solution Property Pages** dialog, under **Common Properties**, **Startup Project**, select **Multiple startup projects:**.</span></span>

4. <span data-ttu-id="d5b13-118">Accanto al **DCSwithDCR** progetto, selezionare **avviare** dal **azione** elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="d5b13-118">Next to the **DCSwithDCR** project, select **Start** from the **Action** dropdown.</span></span>

5. <span data-ttu-id="d5b13-119">Accanto al **NetDCS** progetto, selezionare **avviare** dal **azione** elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="d5b13-119">Next to the **NetDCS** project, select **Start** from the **Action** dropdown.</span></span>

6. <span data-ttu-id="d5b13-120">Fare clic su **OK** per chiudere la finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="d5b13-120">Click **OK** to close the dialog.</span></span>

7. <span data-ttu-id="d5b13-121">Per compilare la soluzione, premere CTRL+MAIUSC+B.</span><span class="sxs-lookup"><span data-stu-id="d5b13-121">To build the solution, press CTRL+SHIFT+B.</span></span>

8. <span data-ttu-id="d5b13-122">Per eseguire la soluzione, premere CTRL+F5.</span><span class="sxs-lookup"><span data-stu-id="d5b13-122">To run the solution, press CTRL+F5.</span></span>

> [!IMPORTANT]
>  <span data-ttu-id="d5b13-123">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="d5b13-123">The samples may already be installed on your machine.</span></span> <span data-ttu-id="d5b13-124">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="d5b13-124">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="d5b13-125">Se questa directory non esiste, andare al [Windows Communication Foundation (WCF) e gli esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti i Windows Communication Foundation (WCF) e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi.</span><span class="sxs-lookup"><span data-stu-id="d5b13-125">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="d5b13-126">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="d5b13-126">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Contract\Data\NetDcSasDcSwithDCR`  
