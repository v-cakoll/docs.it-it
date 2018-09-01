---
title: 'Procedura: definire una stringa di connessione'
ms.date: 03/30/2017
ms.assetid: 6027335d-4e26-420d-9151-6523289b1989
ms.openlocfilehash: f40b8bc68eda1cb4b64b34d12b2922da69929203
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/01/2018
ms.locfileid: "43387754"
---
# <a name="how-to-define-the-connection-string"></a>Procedura: definire una stringa di connessione
In questo argomento viene illustrato come definire la stringa di connessione usata per la connessione a un modello concettuale. In questo argomento si basa sul [Sales di AdventureWorks](https://msdn.microsoft.com/library/f16cd988-673f-4376-b034-129ca93c7832) modello concettuale. Il modello Sales di AdventureWorks viene usato in tutti gli argomenti correlati ad attività inclusi nella documentazione di [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]. Questo argomento si presuppone che si è già configurato il [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] e definito modello Sales di AdventureWorks. Per altre informazioni, vedere [procedura: definire manualmente file di modello e di Mapping](https://msdn.microsoft.com/library/d4fd6864-f2a1-48f0-aa32-1e318775a99a). Le procedure descritte in questo argomento sono incluse anche in [procedura: configurare manualmente un progetto Entity Framework](https://msdn.microsoft.com/library/73f6ae1d-b3b2-4577-aebd-ad5a75954e9e).  
  
> [!NOTE]
>  Se si usa la [!INCLUDE[adonet_edm](../../../../../includes/adonet-edm-md.md)] procedura guidata in un progetto di Visual Studio, viene automaticamente generato un file con estensione edmx e configura il progetto deve utilizzare il [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]. Per altre informazioni, vedere [procedura: usare la procedura guidata Entity Data Model](https://msdn.microsoft.com/library/dadb058a-c5d9-4c5c-8b01-28044112231d)  
  
### <a name="to-define-the-entity-framework-connection-string"></a>Per definire la stringa di connessione Entity Framework  
  
-   Aprire il file di configurazione dell'applicazione (app.config) del progetto e aggiungere la stringa di connessione seguente.  
  
  
  
     Se il progetto non dispone di un file di configurazione dell'applicazione, è possibile aggiungerne uno selezionando **Aggiungi nuovo elemento** dal **Project** dal menu selezionando il **generali** categoria, selezionando **File di configurazione dell'applicazione**e quindi scegliendo **Add**.  
  
## <a name="see-also"></a>Vedere anche  
 [Guida rapida](https://msdn.microsoft.com/library/0bc534be-789f-4819-b9f6-76e51d961675)  
 [Procedura: creare un nuovo File con estensione edmx](https://msdn.microsoft.com/library/beb8189e-e51c-4051-839c-9902c224abf2)  
 [Strumenti di ADO.NET Entity Data Model](https://msdn.microsoft.com/library/91076853-0881-421b-837a-f582f36be527)
