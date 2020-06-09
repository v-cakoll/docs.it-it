---
title: 'Procedura: usare Svcutil.exe per esportare metadati dal codice del servizio compilato'
ms.date: 03/30/2017
ms.assetid: 95d0aed3-16a2-4398-89bb-39418eeb7355
ms.openlocfilehash: 9acefdec63a6f518ead6cdbcb19ebc8c75609dd6
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84595362"
---
# <a name="how-to-use-svcutilexe-to-export-metadata-from-compiled-service-code"></a><span data-ttu-id="8639b-102">Procedura: usare Svcutil.exe per esportare metadati dal codice del servizio compilato</span><span class="sxs-lookup"><span data-stu-id="8639b-102">How to: Use Svcutil.exe to Export Metadata from Compiled Service Code</span></span>
<span data-ttu-id="8639b-103">Svcutil.exe è in grado di esportare metadati per servizi, contratti e tipi di dati in assembly compilati, come segue:</span><span class="sxs-lookup"><span data-stu-id="8639b-103">Svcutil.exe can export metadata for services, contracts, and data types in compiled assemblies, as follows:</span></span>  
  
- <span data-ttu-id="8639b-104">Per esportare metadati per tutti i contratti di servizio compilati per un set di assembly utilizzando Svcutil.exe, specificare gli assembly come parametri di input.</span><span class="sxs-lookup"><span data-stu-id="8639b-104">To export metadata for all compiled service contracts for a set of assemblies using Svcutil.exe, specify the assemblies as input parameters.</span></span> <span data-ttu-id="8639b-105">Questo è il comportamento predefinito.</span><span class="sxs-lookup"><span data-stu-id="8639b-105">This is the default behavior.</span></span>  
  
- <span data-ttu-id="8639b-106">Per esportare metadati per un contratto di servizio utilizzando Svcutil.exe, specificare l'assembly o gli assembly del servizio come parametri di input.</span><span class="sxs-lookup"><span data-stu-id="8639b-106">To export metadata for a compiled service using Svcutil.exe, specify the service assembly or assemblies as input parameters.</span></span> <span data-ttu-id="8639b-107">È necessario utilizzare l'opzione `/serviceName` per indicare il nome di configurazione del servizio che si desidera esportare.</span><span class="sxs-lookup"><span data-stu-id="8639b-107">You must use the `/serviceName` option to indicate the configuration name of the service you want to export.</span></span> <span data-ttu-id="8639b-108">Svcutil.exe carica automaticamente il file di configurazione dell'assembly eseguibile specificato.</span><span class="sxs-lookup"><span data-stu-id="8639b-108">Svcutil.exe automatically loads the configuration file for the specified executable assembly.</span></span>  
  
- <span data-ttu-id="8639b-109">Per esportare tutti i tipi di contratto dati all'interno di un set di assembly, utilizzare l'opzione `/dataContractOnly`.</span><span class="sxs-lookup"><span data-stu-id="8639b-109">To export all data contract types within a set of assemblies, use the `/dataContractOnly` option.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="8639b-110">Usare l'opzione `/reference` per specificare il percorso dei file degli eventuali assembly dipendenti.</span><span class="sxs-lookup"><span data-stu-id="8639b-110">Use the `/reference` option to specify the file paths to any dependent assemblies.</span></span>  
  
### <a name="to-export-metadata-for-compiled-service-contracts"></a><span data-ttu-id="8639b-111">Per esportare metadati per contratti di servizio compilati</span><span class="sxs-lookup"><span data-stu-id="8639b-111">To export metadata for compiled service contracts</span></span>  
  
1. <span data-ttu-id="8639b-112">Compilare le implementazioni del contratto di servizio in una o più librerie di classi.</span><span class="sxs-lookup"><span data-stu-id="8639b-112">Compile your service contract implementations into one or more class libraries.1</span></span>  
  
2. <span data-ttu-id="8639b-113">Eseguire Svcutil.exe sugli assembly compilati.</span><span class="sxs-lookup"><span data-stu-id="8639b-113">Run Svcutil.exe on the compiled assemblies.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="8639b-114">Potrebbe essere necessario usare l'opzione `/reference` per specificare il percorso del file di eventuali assembly dipendenti.</span><span class="sxs-lookup"><span data-stu-id="8639b-114">You might need to use the `/reference` switch to specify the file path to any dependent assemblies.</span></span>  
  
    ```console
    svcutil.exe Contracts.dll  
    ```  
  
### <a name="to-export-metadata-for-a-compiled-service"></a><span data-ttu-id="8639b-115">Per esportare metadati per un servizio compilato</span><span class="sxs-lookup"><span data-stu-id="8639b-115">To export metadata for a compiled service</span></span>  
  
1. <span data-ttu-id="8639b-116">Compilare l'implementazione del servizio in un assembly eseguibile.</span><span class="sxs-lookup"><span data-stu-id="8639b-116">Compile your service implementation into an executable assembly.</span></span>  
  
2. <span data-ttu-id="8639b-117">Creare un file di configurazione per l'eseguibile del servizio e aggiungere una configurazione del servizio.</span><span class="sxs-lookup"><span data-stu-id="8639b-117">Create a configuration file for your service executable and add a service configuration.</span></span>  
  
    ```xml  
    <?xml version="1.0" encoding="utf-8" ?>  
    <configuration>  
      <system.serviceModel>  
        <services>  
          <service name="MyService" >  
            <endpoint address="finder" contract="IPeopleFinder" binding="wsHttpBinding" />  
          </service>  
        </services>  
      </system.serviceModel>  
    </configuration>  
    ```  
  
3. <span data-ttu-id="8639b-118">Eseguire Svcutil.exe sull'eseguibile del servizio compilato utilizzando l'opzione `/serviceName` per specificare il nome di configurazione del servizio.</span><span class="sxs-lookup"><span data-stu-id="8639b-118">Run Svcutil.exe on the compiled service executable using the `/serviceName` switch to specify the configuration name of the service.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="8639b-119">Potrebbe essere necessario usare l'opzione `/reference` per specificare il percorso del file di eventuali assembly dipendenti.</span><span class="sxs-lookup"><span data-stu-id="8639b-119">You might need to use the `/reference` switch to specify the file path to any dependent assemblies.</span></span>  
  
    ```console  
    svcutil.exe /serviceName:MyService Service.exe /reference:path/Contracts.dll  
    ```  
  
### <a name="to-export-metadata-for-compiled-data-contracts"></a><span data-ttu-id="8639b-120">Per esportare metadati per contratti dati compilati</span><span class="sxs-lookup"><span data-stu-id="8639b-120">To export metadata for compiled data contracts</span></span>  
  
1. <span data-ttu-id="8639b-121">Compilare le implementazioni del contratto dati in una o più librerie di classi.</span><span class="sxs-lookup"><span data-stu-id="8639b-121">Compile your data contract implementations into one or more class libraries.</span></span>  
  
2. <span data-ttu-id="8639b-122">Eseguire Svcutil.exe sugli assembly compilati utilizzando l'opzione `/dataContract` per specificare che devono essere generati solo i metadati dei contratti dati.</span><span class="sxs-lookup"><span data-stu-id="8639b-122">Run Svcutil.exe on the compiled assemblies using the `/dataContract` switch to specify that only metadata for data contracts should be generated.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="8639b-123">Potrebbe essere necessario usare l'opzione `/reference` per specificare il percorso del file di eventuali assembly dipendenti.</span><span class="sxs-lookup"><span data-stu-id="8639b-123">You might need to use the `/reference` switch to specify the file path to any dependent assemblies.</span></span>  
  
    ```console  
    svcutil.exe /dataContractOnly Contracts.dll  
    ```  
  
## <a name="example"></a><span data-ttu-id="8639b-124">Esempio</span><span class="sxs-lookup"><span data-stu-id="8639b-124">Example</span></span>  
 <span data-ttu-id="8639b-125">Nell'esempio seguente viene dimostrato come generare metadati per un'implementazione semplice del servizio e una configurazione.</span><span class="sxs-lookup"><span data-stu-id="8639b-125">The following example demonstrates how to generate metadata for a simple service implementation and configuration.</span></span>  
  
 <span data-ttu-id="8639b-126">Per esportare metadati per il contratto di servizio</span><span class="sxs-lookup"><span data-stu-id="8639b-126">To export metadata for the service contract.</span></span>  
  
```console  
svcutil.exe Contracts.dll  
```  
  
 <span data-ttu-id="8639b-127">Per esportare metadati per i contratti dati.</span><span class="sxs-lookup"><span data-stu-id="8639b-127">To export metadata for the data contracts.</span></span>  
  
```console  
svcutil.exe /dataContractOnly Contracts.dll  
```  
  
 <span data-ttu-id="8639b-128">Per esportare metadati per l'implementazione del servizio</span><span class="sxs-lookup"><span data-stu-id="8639b-128">To export metadata for the service implementation.</span></span>  
  
```console  
svcutil.exe /serviceName:MyService Service.exe /reference:<path>/Contracts.dll  
```  
  
 <span data-ttu-id="8639b-129">`<path>` è il percorso di Contracts.dll.</span><span class="sxs-lookup"><span data-stu-id="8639b-129">The `<path>` is the path to Contracts.dll.</span></span>  
  
```csharp
// The following service contract and data contracts are compiled into
// Contracts.dll.  
[ServiceContract(ConfigurationName="IPeopleFinder")]  
public interface IPersonFinder  
{  
    [OperationContract]  
    Address GetAddress(Person s);  
}  
  
[DataContract]  
public class Person  
{  
    [DataMember]  
    public string firstName;  
    [DataMember]  
    public string lastName;  
    [DataMember]  
    public int age;  
}  
  
[DataContract]  
public class Address  
{  
    [DataMember]  
    public string city;  
    [DataMember]  
    public string state;  
    [DataMember]  
    public string street;  
    [DataMember]  
    public int zipCode;  
    [DataMember]  
    public Person person;  
}  
```

```csharp
// The following service implementation is compiled into Service.exe.
// This service uses the contracts specified in Contracts.dll.  
[ServiceBehavior(ConfigurationName = "MyService")]  
public class MyService : IPersonFinder  
{  
    public Address GetAddress(Person person)  
    {  
        Address address = new Address();  
        address.person = person;  
        return address;  
    }  
}  
```

```xml  
<!-- The following is the configuration file for Service.exe. -->  
<?xml version="1.0" encoding="utf-8" ?>  
<configuration>  
  <system.serviceModel>  
    <services>  
      <service name="MyService">  
         <endpoint  address="finder"  
                    binding="basicHttpBinding"  
                    contract="IPeopleFinder"/>  
      </service>  
    </services>  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="8639b-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8639b-130">See also</span></span>

- [<span data-ttu-id="8639b-131">Strumento ServiceModel Metadata Utility Tool (Svcutil.exe)</span><span class="sxs-lookup"><span data-stu-id="8639b-131">ServiceModel Metadata Utility Tool (Svcutil.exe)</span></span>](../servicemodel-metadata-utility-tool-svcutil-exe.md)
- [<span data-ttu-id="8639b-132">Esportazione e importazione di metadati</span><span class="sxs-lookup"><span data-stu-id="8639b-132">Exporting and Importing Metadata</span></span>](exporting-and-importing-metadata.md)
