---
title: 'Procedura: Usare EdmGen.exe per convalidare file di modello e di mapping'
ms.date: 03/30/2017
ms.assetid: 2641906a-971a-4d0b-8aee-13fabc02a1cc
ms.openlocfilehash: ac278123e9b0927ba6b2ce07059561e7fbb3a898
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59329272"
---
# <a name="how-to-use-edmgenexe-to-validate-model-and-mapping-files"></a>Procedura: Usare EdmGen.exe per convalidare file di modello e di mapping
Questo argomento viene illustrato come usare il [generatore EDM (EdmGen.exe)](../../../../../docs/framework/data/adonet/ef/edm-generator-edmgen-exe.md) dello strumento per convalidare il modello e i file di mapping. Per altre informazioni, vedere [Entity Data Model](../../../../../docs/framework/data/adonet/entity-data-model.md).  
  
### <a name="to-validate-the-school-model-using-edmgenexe"></a>Per convalidare il modello School usando EdmGen.exe  
  
1. Creare il database School. Per altre informazioni, vedere [creazione del Database di esempio School](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399731(v=vs.100)).  
  
2. Generare il modello School. Per altre informazioni, vedere [Procedura: Consente di generare il modello e i file di Mapping EdmGen.exe](../../../../../docs/framework/data/adonet/ef/how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md).  
  
3. Al prompt dei comandi eseguire il comando seguente senza interruzioni di riga:  
  
    ```console
    "%windir%\Microsoft.NET\Framework\v4.0.30319\edmgen.exe" /mode:ValidateArtifacts /inssdl:.\School.ssdl /inmsl:.\School.msl /incsdl:.\School.csdl  
    ```  
  
## <a name="see-also"></a>Vedere anche

- [Procedura: Configurare manualmente un progetto Entity Framework](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738546(v=vs.100))
- [Strumenti di ADO.NET Entity Data Model](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399249(v=vs.100))
- [Procedura: Pre-generare viste per migliorare le prestazioni delle Query](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb896240(v=vs.100))
- [Procedura: Usare EdmGen.exe per generare codice del livello oggetti](../../../../../docs/framework/data/adonet/ef/how-to-use-edmgen-exe-to-generate-object-layer-code.md)
