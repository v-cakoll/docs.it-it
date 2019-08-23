---
title: 'Procedura: Generare manualmente classi del servizio dati client (WCF Data Services)'
ms.date: 03/30/2017
helpviewer_keywords:
- WCF Data Services, configuring
- WCF Data Services, client library
ms.assetid: b98cb1d6-956a-4e50-add6-67e4f2587346
ms.openlocfilehash: 2a827e4909b18d9cca74fc20a2d83d2730ea0cd9
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69952290"
---
# <a name="how-to-manually-generate-client-data-service-classes-wcf-data-services"></a>Procedura: Generare manualmente classi del servizio dati client (WCF Data Services)
WCF Data Services si integra con Visual Studio per consentire la generazione automatica di classi del servizio dati client quando si utilizza la finestra di dialogo **Aggiungi riferimento al servizio** per aggiungere un riferimento a un servizio dati in un progetto di Visual Studio. Per altre informazioni, vedere [Procedura: Aggiungere un riferimento](../../../../docs/framework/data/wcf/how-to-add-a-data-service-reference-wcf-data-services.md)al servizio dati. È inoltre possibile generare in modo manuale le stesse classi del servizio dati client utilizzando lo strumento per la generazione del codice, ovvero `DataSvcUtil.exe`. Questo strumento, incluso con WCF Data Services, genera .NET Framework classi dalla definizione del servizio dati. Può inoltre essere usato per generare classi del servizio dati in base al file del modello concettuale (CSDL) e al file con estensione edmx che rappresenta un modello di Entity Framework in un progetto di Visual Studio.

 Nell'esempio riportato in questo argomento vengono create le classi del servizio dati client in base al servizio dati Northwind di esempio. Questo servizio viene creato al completamento della [WCF Data Services Guida introduttiva](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md). Per alcuni esempi inclusi in questo argomento è richiesto il file del modello concettuale per il modello Northwind. Per altre informazioni, vedere [Procedura: Utilizzare EdmGen. exe per generare i file](../../../../docs/framework/data/adonet/ef/how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md)di modello e di mapping. Per alcuni esempi inclusi in questo argomento è richiesto il file con estensione edmx per il modello Northwind. Per ulteriori informazioni, vedere [Cenni preliminari sui file](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cc982042(v=vs.100))con estensione edmx.

### <a name="to-generate-c-classes-that-support-data-binding"></a>Per generare classi C# che supportano l'associazione dati

- Al prompt dei comandi eseguire il comando seguente senza interruzioni di riga:

    ```console
    "%windir%\Microsoft.NET\Framework\v3.5\DataSvcUtil.exe" /dataservicecollection /version:2.0 /language:CSharp /out:Northwind.cs /uri:http://localhost:12345/Northwind.svc
    ```

    > [!NOTE]
    > È necessario sostituire il valore fornito al parametro `/uri:` con l'URI dell'istanza del servizio dati Northwind di esempio.

### <a name="to-generate-visual-basic-classes-that-support-data-binding"></a>Per generare classi Visual Basic che supportano il data binding

- Al prompt dei comandi eseguire il comando seguente senza interruzioni di riga:

    ```console
    "%windir%\Microsoft.NET\Framework\v3.5\DataSvcUtil.exe" /dataservicecollection /version:2.0 /language:VB /out:Northwind.vb /uri:http://localhost:12345/Northwind.svc
    ```

    > [!NOTE]
    > È necessario sostituire il valore fornito al parametro `/uri:` con l'URI dell'istanza del servizio dati Northwind di esempio.

### <a name="to-generate-c-classes-based-on-the-service-uri"></a>Per generare classi C# basate sull'URI del servizio

- Al prompt dei comandi eseguire il comando seguente senza interruzioni di riga:

    ```
    "%windir%\Microsoft.NET\Framework\v3.5\DataSvcUtil.exe" /language:CSharp /out:northwind.cs /uri:http://localhost:12345/Northwind.svc
    ```

    > [!NOTE]
    > È necessario sostituire il valore fornito al parametro `/uri:` con l'URI dell'istanza del servizio dati Northwind di esempio.

### <a name="to-generate-visual-basic-classes-based-on-the-service-uri"></a>Per generare classi Visual Basic basate sull'URI del servizio

- Al prompt dei comandi eseguire il comando seguente senza interruzioni di riga:

    ```
    "%windir%\Microsoft.NET\Framework\v3.5\datasvcutil.exe" /language:VB /out:Northwind.vb /uri:http://localhost:12345/Northwind.svc
    ```

    > [!NOTE]
    > È necessario sostituire il valore fornito al parametro `/uri:` con l'URI dell'istanza del servizio dati Northwind di esempio.

### <a name="to-generate-c-classes-based-on-the-conceptual-model-file-csdl"></a>Per generare classi C# basate sul file del modello concettuale (CSDL)

- Al prompt dei comandi eseguire il comando seguente senza interruzioni di riga:

    ```
    "%windir%\Microsoft.NET\Framework\v3.5\datasvcutil.exe" /language:CSharp /in:Northwind.csdl /out:Northwind.cs
    ```

### <a name="to-generate-visual-basic-classes-based-on-the-conceptual-model-file-csdl"></a>Per generare classi Visual Basic basate sul file del modello concettuale (CSDL)

- Al prompt dei comandi eseguire il comando seguente senza interruzioni di riga:

    ```
    "%windir%\Microsoft.NET\Framework\v3.5\datasvcutil.exe" /language:VB /in:Northwind.csdl /out:Northwind.vb
    ```

### <a name="to-generate-c-classes-based-on-the-edmx-file"></a>Per generare classi C# basate sul file con estensione edmx

- Al prompt dei comandi eseguire il comando seguente senza interruzioni di riga:

    ```
    "%windir%\Microsoft.NET\Framework\v3.5\datasvcutil.exe" /language:CSharp /in:Northwind.edmx /out:c:\northwind.cs
    ```

### <a name="to-generate-visual-basic-classes-based-on-the-edmx-file"></a>Per generare classi Visual Basic basate sul file con estensione edmx

- Al prompt dei comandi eseguire il comando seguente senza interruzioni di riga:

    ```
    "%windir%\Microsoft.NET\Framework\v3.5\datasvcutil.exe" /language:VB /in:Northwind.edmx /out:c:\northwind.vb
    ```

## <a name="see-also"></a>Vedere anche

- [Generazione della libreria client del servizio dati](../../../../docs/framework/data/wcf/generating-the-data-service-client-library-wcf-data-services.md)
- [Procedura: Aggiungere un riferimento al servizio dati](../../../../docs/framework/data/wcf/how-to-add-a-data-service-reference-wcf-data-services.md)
- [Utilità client WCF Data Services (DataSvcUtil.exe)](../../../../docs/framework/data/wcf/wcf-data-service-client-utility-datasvcutil-exe.md)
