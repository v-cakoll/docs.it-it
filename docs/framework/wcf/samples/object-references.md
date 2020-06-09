---
title: Riferimenti a oggetti
ms.date: 03/30/2017
ms.assetid: 7a93d260-91c3-4448-8f7a-a66fb562fc23
ms.openlocfilehash: ba4ee3fd0cc16130f66570891ecc295b2d2c50aa
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84599984"
---
# <a name="object-references"></a><span data-ttu-id="e0f47-102">Riferimenti a oggetti</span><span class="sxs-lookup"><span data-stu-id="e0f47-102">Object References</span></span>
<span data-ttu-id="e0f47-103">In questo esempio viene illustrato come passare oggetti mediante riferimenti tra server e client.</span><span class="sxs-lookup"><span data-stu-id="e0f47-103">This sample demonstrates how to pass objects by references between server and client.</span></span> <span data-ttu-id="e0f47-104">Nell'esempio vengono utilizzati i *Social Network*simulati.</span><span class="sxs-lookup"><span data-stu-id="e0f47-104">The sample uses simulated *social networks*.</span></span> <span data-ttu-id="e0f47-105">Una social network è costituita da una classe `Person` che contiene un elenco di amici in cui ogni amico è un'istanza della classe `Person`, con il proprio elenco di amici.</span><span class="sxs-lookup"><span data-stu-id="e0f47-105">A social network consists of a `Person` class that contains a list of friends in which each friend is an instance of the `Person` class, with its own list of friends.</span></span> <span data-ttu-id="e0f47-106">Viene creato un grafico degli oggetti.</span><span class="sxs-lookup"><span data-stu-id="e0f47-106">This creates a graph of objects.</span></span> <span data-ttu-id="e0f47-107">Il servizio espone le operazioni in tali social network.</span><span class="sxs-lookup"><span data-stu-id="e0f47-107">The service exposes operations on these social networks.</span></span>  
  
 <span data-ttu-id="e0f47-108">In questo esempio, il servizio è ospitato da Internet Information Services (IIS) e il client è un'applicazione console (.exe).</span><span class="sxs-lookup"><span data-stu-id="e0f47-108">In this sample, the service is hosted by Internet Information Services (IIS) and the client is a console application (.exe).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e0f47-109">La procedura di installazione e le istruzioni di compilazione per questo esempio si trovano alla fine di questo argomento.</span><span class="sxs-lookup"><span data-stu-id="e0f47-109">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
## <a name="service"></a><span data-ttu-id="e0f47-110">Service</span><span class="sxs-lookup"><span data-stu-id="e0f47-110">Service</span></span>  
 <span data-ttu-id="e0f47-111">Alla classe `Person` è applicato l'attributo <xref:System.Runtime.Serialization.DataContractAttribute>, con il campo <xref:System.Runtime.Serialization.DataContractAttribute.IsReference%2A> impostato su `true` per dichiararlo come tipo di riferimento.</span><span class="sxs-lookup"><span data-stu-id="e0f47-111">The `Person` class has the <xref:System.Runtime.Serialization.DataContractAttribute> attribute applied, with the <xref:System.Runtime.Serialization.DataContractAttribute.IsReference%2A> field set to `true` to declare it as a reference type.</span></span> <span data-ttu-id="e0f47-112">A tutte le proprietà è applicato l'attributo <xref:System.Runtime.Serialization.DataMemberAttribute>.</span><span class="sxs-lookup"><span data-stu-id="e0f47-112">All properties have the <xref:System.Runtime.Serialization.DataMemberAttribute> attribute applied.</span></span>  
  
```csharp
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
  
 <span data-ttu-id="e0f47-113">L'operazione `GetPeopleInNetwork` accetta un parametro di tipo `Person` e restituisce tutte le persone nella rete, ovvero tutte le persone nell'elenco `friends`, gli amici degli amici e così via, senza duplicati.</span><span class="sxs-lookup"><span data-stu-id="e0f47-113">The `GetPeopleInNetwork` operation takes a parameter of type `Person` and returns all the people in the network; that is, all the people in the `friends` list, the friend's friends, and so on, without duplicates.</span></span>  
  
```csharp
public List<Person> GetPeopleInNetwork(Person p)  
{  
    List<Person> people = new List<Person>();  
    ListPeopleInNetwork(p, people);  
    return people;  
  
}  
```  
  
 <span data-ttu-id="e0f47-114">L'operazione `GetMutualFriends` accetta un parametro di tipo `Person` e restituisce tutti gli amici nell'elenco nei cui elenchi `friends` è inclusa questa persona.</span><span class="sxs-lookup"><span data-stu-id="e0f47-114">The `GetMutualFriends` operation takes a parameter of type `Person` and returns all the friends in the list who also have this person in their `friends` list.</span></span>  
  
```csharp
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
  
 <span data-ttu-id="e0f47-115">L'operazione `GetCommonFriends` accetta un elenco di tipo `Person`.</span><span class="sxs-lookup"><span data-stu-id="e0f47-115">The `GetCommonFriends` operation takes a list of type `Person`.</span></span> <span data-ttu-id="e0f47-116">È previsto che l'elenco contenga due oggetti `Person`.</span><span class="sxs-lookup"><span data-stu-id="e0f47-116">The list is expected to have two `Person` objects in it.</span></span> <span data-ttu-id="e0f47-117">L'operazione restituisce un elenco di oggetti `Person` inclusi negli elenchi `friends` di entrambi gli oggetti `Person` nell'elenco di input.</span><span class="sxs-lookup"><span data-stu-id="e0f47-117">The operation returns a list of `Person` objects that are in the `friends` lists of both `Person` objects in the input list.</span></span>  
  
```csharp
public List<Person> GetCommonFriends(List<Person> people)  
{  
    List<Person> common = new List<Person>();  
    foreach (Person friend in people[0].Friends)  
        if (people[1].Friends.Contains(friend))  
            common.Add(friend);  
    return common;  
}  
```  
  
## <a name="client"></a><span data-ttu-id="e0f47-118">Client</span><span class="sxs-lookup"><span data-stu-id="e0f47-118">Client</span></span>  
 <span data-ttu-id="e0f47-119">Il proxy client viene creato usando la funzionalità **Aggiungi riferimento al servizio** di Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="e0f47-119">The client proxy is created using the **Add Service Reference** feature of Visual Studio.</span></span>  
  
 <span data-ttu-id="e0f47-120">Viene creata una social network costituita da cinque oggetti `Person`.</span><span class="sxs-lookup"><span data-stu-id="e0f47-120">A social network that consists of five `Person` objects is created.</span></span> <span data-ttu-id="e0f47-121">Il client chiama ognuno dei tre metodi nel servizio.</span><span class="sxs-lookup"><span data-stu-id="e0f47-121">The client calls each of the three methods in the service.</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="e0f47-122">Per impostare, compilare ed eseguire l'esempio</span><span class="sxs-lookup"><span data-stu-id="e0f47-122">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="e0f47-123">Assicurarsi di avere eseguito la [procedura di installazione singola per gli esempi di Windows Communication Foundation](one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="e0f47-123">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="e0f47-124">Per compilare l'edizione in C# o Visual Basic .NET della soluzione, seguire le istruzioni in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="e0f47-124">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span></span>  
  
3. <span data-ttu-id="e0f47-125">Per eseguire l'esempio in una configurazione con un solo computer o tra computer diversi, seguire le istruzioni in [esecuzione degli esempi di Windows Communication Foundation](running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="e0f47-125">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="e0f47-126">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="e0f47-126">The samples may already be installed on your machine.</span></span> <span data-ttu-id="e0f47-127">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="e0f47-127">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="e0f47-128">Se questa directory non esiste, passare a [Windows Communication Foundation (WCF) ed esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) per scaricare tutti i Windows Communication Foundation (WCF) ed [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi.</span><span class="sxs-lookup"><span data-stu-id="e0f47-128">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="e0f47-129">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="e0f47-129">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Contract\Data\ObjectReferences`  
  
## <a name="see-also"></a><span data-ttu-id="e0f47-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e0f47-130">See also</span></span>

- <xref:System.Runtime.Serialization.DataContractAttribute.IsReference%2A>
- [<span data-ttu-id="e0f47-131">Riferimenti a oggetti interoperativi</span><span class="sxs-lookup"><span data-stu-id="e0f47-131">Interoperable Object References</span></span>](../feature-details/interoperable-object-references.md)
