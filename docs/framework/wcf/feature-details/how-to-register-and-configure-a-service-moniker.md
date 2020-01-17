---
title: 'Procedura: registrare e configurare un moniker servizio'
ms.date: 03/30/2017
helpviewer_keywords:
- COM [WCF], configure service monikers
- COM [WCF], register service monikers
ms.assetid: e5e16c80-8a8e-4eef-af53-564933b651ef
ms.openlocfilehash: c68ca0f7c95515a0552b7003454dd87804176d3d
ms.sourcegitcommit: 09b4090b78f52fd09b0e430cd4b26576f1fdf96e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/17/2020
ms.locfileid: "76212208"
---
# <a name="how-to-register-and-configure-a-service-moniker"></a>Procedura: registrare e configurare un moniker servizio
Prima di utilizzare il moniker del servizio Windows Communication Foundation (WCF) in un'applicazione COM con un contratto tipizzato, è necessario registrare i tipi con attributi necessari con COM e configurare l'applicazione COM e il moniker con l'associazione obbligatoria configurazione.  
  
### <a name="to-register-the-required-attributed-types-with-com"></a>Per registrare i tipi con attributi necessari con COM  
  
1. Utilizzare lo strumento [ServiceModel Metadata Utility Tool (Svcutil. exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) per recuperare il contratto di metadati dal servizio WCF. Viene generato il codice sorgente per un assembly client WCF e un file di configurazione dell'applicazione client.  
  
2. Assicurarsi che i tipi nell'assembly siano contrassegnati come `ComVisible`. A tale scopo, aggiungere l'attributo seguente al file AssemblyInfo.cs nel progetto di Visual Studio.  
  
    ```csharp
    [assembly: ComVisible(true)]  
    ```  
  
3. Compilare il client WCF gestito come assembly con nome sicuro. Ciò richiede una firma con una coppia di chiavi di crittografia. Per altre informazioni, vedere [Firma di un assembly con un nome sicuro](../../../standard/assembly/sign-strong-name.md).  
  
4. Usare lo strumento di registrazione degli assembly (Regasm.exe) con l'opzione `/tlb`, per registrare i tipi nell'assembly con COM.  
  
5. Usare lo strumento della cache di assembly globale (Gacutil.exe) per aggiungere l'assembly alla cache di assembly globale.  
  
    > [!NOTE]
    > La firma e l'aggiunta dell'assembly alla cache di assembly globale sono passaggi facoltativi, che possono però semplificare il processo di caricamento dell'assembly dal percorso corretto in fase di esecuzione.  
  
### <a name="to-configure-the-com-application-and-the-moniker-with-the-required-binding-configuration"></a>Per configurare l'applicazione COM e il moniker con la configurazione dell'associazione necessaria  
  
- Posizionare le definizioni di binding (generate dallo [strumento ServiceModel Metadata Utility Tool (Svcutil. exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) nel file di configurazione dell'applicazione client generato nel file di configurazione dell'applicazione client. Ad esempio, per il file eseguibile di Visual Basic 6.0 denominato CallCenterClient.exe, la configurazione deve essere posizionata in un file denominato CallCenterConfig.exe.config all'interno della stessa directory del file eseguibile. L'applicazione client può ora usare il moniker. Si noti che la configurazione dell'associazione non è necessaria se si utilizza uno dei tipi di binding standard forniti da WCF.  
  
     Viene registrato il tipo seguente.  
  
    ```csharp  
    using System.ServiceModel;  
  
    [ServiceContract]   
    public interface IMathService   
    {  
    [OperationContract]  
    public int Add(int x, int y);  
    [OperationContract]  
    public int Subtract(int x, int y);  
    }  
    ```  
  
     L'applicazione viene esposta usando un'associazione `wsHttpBinding`. Per il tipo e la configurazione dell'applicazione specificati, vengono usate le stringhe del moniker di esempio seguenti.  
  
    ``` 
    service4:address=http://localhost/MathService, binding=wsHttpBinding, bindingConfiguration=Binding1  
    ```  
  
     `or`  
  
    ``` 
    service4:address=http://localhost/MathService, binding=wsHttpBinding, bindingConfiguration=Binding1, contract={36ADAD5A-A944-4d5c-9B7C-967E4F00A090}  
    ```  
  
     È possibile usare entrambe le stringhe del moniker dall'interno dell'applicazione Visual Basic 6.0, dopo avere aggiunto un riferimento all'assembly contenente i tipi `IMathService`, come illustrato nel codice di esempio seguente.  
  
    ```vb
    Dim MathProxy As IMathService  
    Dim result As Integer  
  
    Set MathProxy = GetObject( _  
            "service4:address=http://localhost/MathService, _  
            binding=wsHttpBinding, _  
            bindingConfiguration=Binding1")  
  
    result = MathProxy.Add(3, 5)  
    ```  
  
     In questo esempio, la definizione per la configurazione dell'associazione `Binding1` viene archiviata in un file di configurazione adeguatamente denominato per l'applicazione client, ad esempio vb6appname.exe.config.  
  
    > [!NOTE]
    > È possibile usare codice simile in C#, C++ o in qualsiasi altra applicazione del linguaggio .NET.  
  
    > [!NOTE]
    > Se il formato del moniker non è valido o il servizio non è disponibile, la chiamata a `GetObject` restituirà un errore di sintassi non valida. Se si riceve questo errore, verificare che il moniker che si sta usando sia valido e che il servizio sia disponibile.  
  
     Sebbene questo argomento sia incentrato sull'utilizzo del moniker del servizio dal codice Visual Basic 6,0, è possibile utilizzare un moniker di servizio da altri linguaggi. Quando si usa un moniker da codice C++, l'assembly generato da Svcutil.exe deve essere importato con "no_namespace named_guids raw_interfaces_only", come illustrato nel codice seguente.  
  
    ```cpp
    #import "ComTestProxy.tlb" no_namespace named_guids  
    ```  
  
     Ciò modifica le definizioni dell'interfaccia importate, in modo che tutti i metodi restituiscano un `HResult`. Tutti gli altri valori restituiti vengono convertiti in parametri out. L'esecuzione complessiva dei metodi resta la stessa. Questo consente di determinare la causa di un'eccezione quando si chiama un metodo sul proxy. Questa funzionalità è disponibile solo da codice C++.  
  
## <a name="see-also"></a>Vedere anche

- [Strumento ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)
