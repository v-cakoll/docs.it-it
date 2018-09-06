---
title: Riferimenti a oggetti
ms.date: 03/30/2017
ms.assetid: 7a93d260-91c3-4448-8f7a-a66fb562fc23
ms.openlocfilehash: 1aa8b1c9d135186dba9e4da75f0c7cb9297d8e5c
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/05/2018
ms.locfileid: "43787220"
---
# <a name="object-references"></a>Riferimenti a oggetti
In questo esempio viene illustrato come passare oggetti mediante riferimenti tra server e client. L'esempio Usa simulata *social network*. Una social network è costituita da una classe `Person` che contiene un elenco di amici in cui ogni amico è un'istanza della classe `Person`, con il proprio elenco di amici. Viene creato un grafico degli oggetti. Il servizio espone le operazioni in tali social network.  
  
 In questo esempio, il servizio è ospitato da Internet Information Services (IIS) e il client è un'applicazione console (.exe).  
  
> [!NOTE]
>  La procedura di installazione e le istruzioni di compilazione per questo esempio si trovano alla fine di questo argomento.  
  
## <a name="service"></a>Service  
 Alla classe `Person` è applicato l'attributo <xref:System.Runtime.Serialization.DataContractAttribute>, con il campo <xref:System.Runtime.Serialization.DataContractAttribute.IsReference%2A> impostato su `true` per dichiararlo come tipo di riferimento. A tutte le proprietà è applicato l'attributo <xref:System.Runtime.Serialization.DataMemberAttribute>.  
  
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
  
 L'operazione `GetPeopleInNetwork` accetta un parametro di tipo `Person` e restituisce tutte le persone nella rete, ovvero tutte le persone nell'elenco `friends`, gli amici degli amici e così via, senza duplicati.  
  
```  
public List<Person> GetPeopleInNetwork(Person p)  
{  
    List<Person> people = new List<Person>();  
    ListPeopleInNetwork(p, people);  
    return people;  
  
}  
```  
  
 L'operazione `GetMutualFriends` accetta un parametro di tipo `Person` e restituisce tutti gli amici nell'elenco nei cui elenchi `friends` è inclusa questa persona.  
  
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
  
 L'operazione `GetCommonFriends` accetta un elenco di tipo `Person`. È previsto che l'elenco contenga due oggetti `Person`. L'operazione restituisce un elenco di oggetti `Person` inclusi negli elenchi `friends` di entrambi gli oggetti `Person` nell'elenco di input.  
  
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
  
## <a name="client"></a>Client  
 Il proxy client viene creato usando il **Aggiungi riferimento al servizio** funzionalità di Visual Studio.  
  
 Viene creata una social network costituita da cinque oggetti `Person`. Il client chiama ognuno dei tre metodi nel servizio.  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>Per impostare, compilare ed eseguire l'esempio  
  
1.  Assicurarsi di avere eseguito il [monouso procedura di installazione per gli esempi di Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2.  Per compilare l'edizione in C# o Visual Basic .NET della soluzione, seguire le istruzioni in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
3.  Per eseguire l'esempio in una configurazione singola o tra computer, seguire le istruzioni in [esegue gli esempi di Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
> [!IMPORTANT]
>  È possibile che gli esempi siano già installati nel computer. Verificare la directory seguente (impostazione predefinita) prima di continuare.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Se questa directory non esiste, andare al [Windows Communication Foundation (WCF) e gli esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti i Windows Communication Foundation (WCF) e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi. Questo esempio si trova nella directory seguente.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Contract\Data\ObjectReferences`  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Runtime.Serialization.DataContractAttribute.IsReference%2A>  
 [Riferimenti a oggetti interoperativi](../../../../docs/framework/wcf/feature-details/interoperable-object-references.md)
