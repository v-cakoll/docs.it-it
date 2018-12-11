---
title: 'Procedura: Definire la stringa di connessione'
ms.date: 03/30/2017
ms.assetid: 6027335d-4e26-420d-9151-6523289b1989
ms.openlocfilehash: 7fb722acbb13b3502d004978581701cc70118ff8
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/10/2018
ms.locfileid: "53129688"
---
# <a name="how-to-define-the-connection-string"></a>Procedura: Definire la stringa di connessione

In questo argomento viene illustrato come definire la stringa di connessione usata per la connessione a un modello concettuale. In questo argomento si basa sul [Sales di AdventureWorks](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb387147(v=vs.100)) modello concettuale. Il modello Sales di AdventureWorks viene usato in tutti gli argomenti correlati ad attività inclusi nella documentazione di [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]. Questo argomento si presuppone che si è già configurato il [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] e definito modello Sales di AdventureWorks. Per altre informazioni, vedere [come: File di Mapping e definire il modello manualmente](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399785(v=vs.100)). Le procedure descritte in questo argomento sono incluse anche in [come: Configurare manualmente un progetto Entity Framework](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738546(v=vs.100)).

> [!NOTE]
> Se si usa la [!INCLUDE[adonet_edm](../../../../../includes/adonet-edm-md.md)] procedura guidata in un progetto di Visual Studio, viene automaticamente generato un file con estensione edmx e configura il progetto deve utilizzare il [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]. Per altre informazioni, vedere [come: Usare la procedura guidata Entity Data Model](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738677(v=vs.100))

## <a name="to-define-the-entity-framework-connection-string"></a>Per definire la stringa di connessione Entity Framework

- Aprire il file di configurazione dell'applicazione (app.config) del progetto e aggiungere la stringa di connessione seguente.

```xml
<connectionStrings>
    <add name="AdventureWorksEntities" 
         connectionString="metadata=.\AdventureWorks.csdl|.\AdventureWorks.ssdl|.\AdventureWorks.msl;
         provider=System.Data.SqlClient;provider connection string='Data Source=localhost;
         Initial Catalog=AdventureWorks;Integrated Security=True;Connection Timeout=60;
         multipleactiveresultsets=true'" providerName="System.Data.EntityClient" />
</connectionStrings>
```

Se il progetto non dispone di un file di configurazione dell'applicazione, è possibile aggiungerne uno selezionando **Aggiungi nuovo elemento** dal **Project** dal menu selezionando il **generali** categoria, selezionando **File di configurazione dell'applicazione**e quindi scegliendo **Add**.

## <a name="see-also"></a>Vedere anche

- [Guida rapida](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399182(v=vs.100))
- [Come si fa: Creare un nuovo File con estensione edmx](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cc716703(v=vs.100))
- [Strumenti di ADO.NET Entity Data Model](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399249(v=vs.100))
