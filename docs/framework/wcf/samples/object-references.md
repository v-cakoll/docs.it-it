---
title: Riferimenti a oggetti
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7a93d260-91c3-4448-8f7a-a66fb562fc23
caps.latest.revision: 10
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: fcb34efeb7eed28f85774dc5489b3e56aeac4e6c
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/26/2018
---
# <a name="object-references"></a><span data-ttu-id="8787a-102">Riferimenti a oggetti</span><span class="sxs-lookup"><span data-stu-id="8787a-102">Object References</span></span>
<span data-ttu-id="8787a-103">In questo esempio viene illustrato come passare oggetti mediante riferimenti tra server e client.</span><span class="sxs-lookup"><span data-stu-id="8787a-103">This sample demonstrates how to pass objects by references between server and client.</span></span> <span data-ttu-id="8787a-104">L'esempio utilizza simulato *social network*.</span><span class="sxs-lookup"><span data-stu-id="8787a-104">The sample uses simulated *social networks*.</span></span> <span data-ttu-id="8787a-105">Una social network è costituita da una classe `Person` che contiene un elenco di amici in cui ogni amico è un'istanza della classe `Person`, con il proprio elenco di amici.</span><span class="sxs-lookup"><span data-stu-id="8787a-105">A social network consists of a `Person` class that contains a list of friends in which each friend is an instance of the `Person` class, with its own list of friends.</span></span> <span data-ttu-id="8787a-106">Viene creato un grafico degli oggetti.</span><span class="sxs-lookup"><span data-stu-id="8787a-106">This creates a graph of objects.</span></span> <span data-ttu-id="8787a-107">Il servizio espone le operazioni in tali social network.</span><span class="sxs-lookup"><span data-stu-id="8787a-107">The service exposes operations on these social networks.</span></span>  
  
 <span data-ttu-id="8787a-108">In questo esempio, il servizio è ospitato da Internet Information Services (IIS) e il client è un'applicazione console (.exe).</span><span class="sxs-lookup"><span data-stu-id="8787a-108">In this sample, the service is hosted by Internet Information Services (IIS) and the client is a console application (.exe).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8787a-109">La procedura di installazione e le istruzioni di compilazione per questo esempio si trovano alla fine di questo argomento.</span><span class="sxs-lookup"><span data-stu-id="8787a-109">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
## <a name="service"></a><span data-ttu-id="8787a-110">Service</span><span class="sxs-lookup"><span data-stu-id="8787a-110">Service</span></span>  
 <span data-ttu-id="8787a-111">Alla classe `Person` è applicato l'attributo <xref:System.Runtime.Serialization.DataContractAttribute>, con il campo <xref:System.Runtime.Serialization.DataContractAttribute.IsReference%2A> impostato su `true` per dichiararlo come tipo di riferimento.</span><span class="sxs-lookup"><span data-stu-id="8787a-111">The `Person` class has the <xref:System.Runtime.Serialization.DataContractAttribute> attribute applied, with the <xref:System.Runtime.Serialization.DataContractAttribute.IsReference%2A> field set to `true` to declare it as a reference type.</span></span> <span data-ttu-id="8787a-112">A tutte le proprietà è applicato l'attributo <xref:System.Runtime.Serialization.DataMemberAttribute>.</span><span class="sxs-lookup"><span data-stu-id="8787a-112">All properties have the <xref:System.Runtime.Serialization.DataMemberAttribute> attribute applied.</span></span>  
  
```  
[DataContract(IsReference=true)]  
public class Person  
{  
    string name;  
    string location;  
    string gender;  
    int age;  
    List<Person> friends;  
    [DataMember()]  
    public string Name  
    {  
        get { return name; }  
        set { name = value; }  
    }  
    [DataMember()]  
    public string Location  
    {  
        get { return location; }  
        set { location = value; }  
    }  
    [DataMember()]  
    public string Gender  
    {  
        get { return gender; }  
        set { gender = value; }  
    }  
…  
}  
```  
  
 <span data-ttu-id="8787a-113">L'operazione `GetPeopleInNetwork` accetta un parametro di tipo `Person` e restituisce tutte le persone nella rete, ovvero tutte le persone nell'elenco `friends`, gli amici degli amici e così via, senza duplicati.</span><span class="sxs-lookup"><span data-stu-id="8787a-113">The `GetPeopleInNetwork` operation takes a parameter of type `Person` and returns all the people in the network; that is, all the people in the `friends` list, the friend's friends, and so on, without duplicates.</span></span>  
  
```  
public List<Person> GetPeopleInNetwork(Person p)  
{  
    List<Person> people = new List<Person>();  
    ListPeopleInNetwork(p, people);  
    return people;  
  
}  
```  
  
 <span data-ttu-id="8787a-114">L'operazione `GetMutualFriends` accetta un parametro di tipo `Person` e restituisce tutti gli amici nell'elenco nei cui elenchi `friends` è inclusa questa persona.</span><span class="sxs-lookup"><span data-stu-id="8787a-114">The `GetMutualFriends` operation takes a parameter of type `Person` and returns all the friends in the list who also have this person in their `friends` list.</span></span>  
  
```  
public List<Person> GetMutualFriends(Person p)  
{  
    List<Person> mutual = new List<Person>();  
    foreach (Person friend in p.Friends)  
    {  
        if (friend.Friends.Contains(p))  
            mutual.Add(friend);  
    }  
    return mutual;  
}  
```  
  
 <span data-ttu-id="8787a-115">L'operazione `GetCommonFriends` accetta un elenco di tipo `Person`.</span><span class="sxs-lookup"><span data-stu-id="8787a-115">The `GetCommonFriends` operation takes a list of type `Person`.</span></span> <span data-ttu-id="8787a-116">È previsto che l'elenco contenga due oggetti `Person`.</span><span class="sxs-lookup"><span data-stu-id="8787a-116">The list is expected to have two `Person` objects in it.</span></span> <span data-ttu-id="8787a-117">L'operazione restituisce un elenco di oggetti `Person` inclusi negli elenchi `friends` di entrambi gli oggetti `Person` nell'elenco di input.</span><span class="sxs-lookup"><span data-stu-id="8787a-117">The operation returns a list of `Person` objects that are in the `friends` lists of both `Person` objects in the input list.</span></span>  
  
```  
public List<Person> GetCommonFriends(List<Person> people)  
{  
    List<Person> common = new List<Person>();  
    foreach (Person friend in people[0].Friends)  
        if (people[1].Friends.Contains(friend))  
            common.Add(friend);  
    return common;  
}  
```  
  
## <a name="client"></a><span data-ttu-id="8787a-118">Client</span><span class="sxs-lookup"><span data-stu-id="8787a-118">Client</span></span>  
 <span data-ttu-id="8787a-119">Il proxy del client viene creato utilizzando il **Aggiungi riferimento al servizio** funzionalità di Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="8787a-119">The client proxy is created using the **Add Service Reference** feature of Visual Studio.</span></span>  
  
 <span data-ttu-id="8787a-120">Viene creata una social network costituita da cinque oggetti `Person`.</span><span class="sxs-lookup"><span data-stu-id="8787a-120">A social network that consists of five `Person` objects is created.</span></span> <span data-ttu-id="8787a-121">Il client chiama ognuno dei tre metodi nel servizio.</span><span class="sxs-lookup"><span data-stu-id="8787a-121">The client calls each of the three methods in the service.</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="8787a-122">Per impostare, compilare ed eseguire l'esempio</span><span class="sxs-lookup"><span data-stu-id="8787a-122">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="8787a-123">Assicurarsi di avere eseguito la [procedura di installazione singola per gli esempi di Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="8787a-123">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2.  <span data-ttu-id="8787a-124">Per compilare l'edizione in C# o Visual Basic .NET della soluzione, seguire le istruzioni in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="8787a-124">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3.  <span data-ttu-id="8787a-125">Per eseguire l'esempio in una configurazione singola o tra computer, seguire le istruzioni in [esegue gli esempi di Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="8787a-125">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="8787a-126">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="8787a-126">The samples may already be installed on your machine.</span></span> <span data-ttu-id="8787a-127">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="8787a-127">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="8787a-128">Se questa directory non esiste, andare alla sezione relativa agli [esempi di Windows Communication Foundation (WCF) e Windows Workflow Foundation (WF) per .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti gli esempi di [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="8787a-128">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="8787a-129">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="8787a-129">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Contract\Data\ObjectReferences`  
  
## <a name="see-also"></a><span data-ttu-id="8787a-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8787a-130">See Also</span></span>  
 <xref:System.Runtime.Serialization.DataContractAttribute.IsReference%2A>  
 [<span data-ttu-id="8787a-131">Riferimenti a oggetti interoperativi</span><span class="sxs-lookup"><span data-stu-id="8787a-131">Interoperable Object References</span></span>](../../../../docs/framework/wcf/feature-details/interoperable-object-references.md)
