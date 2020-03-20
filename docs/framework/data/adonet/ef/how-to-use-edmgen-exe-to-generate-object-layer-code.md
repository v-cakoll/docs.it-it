---
title: 'Procedura: utilizzare EdmGen.exe per generare codice a livello oggetti'
ms.date: 03/30/2017
ms.assetid: c44d2ebe-f66f-42cb-9741-4a3f0c2dcffb
ms.openlocfilehash: 1dbd2e25d5f9795af4f80e079c6a0b807666743d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79150558"
---
# <a name="how-to-use-edmgenexe-to-generate-object-layer-code"></a>Procedura: utilizzare EdmGen.exe per generare codice a livello oggetti
In questo argomento viene illustrato come utilizzare lo strumento [Generatore EDM (EdmGen.exe)](edm-generator-edmgen-exe.md) per generare codice a livello di oggetto basato sul file con estensione csdl.  
  
### <a name="to-generate-object-layer-code-for-the-school-model-for-a-visual-basic-project-using-edmgenexe"></a>Per generare il codice del livello oggetti per il modello School per un progetto di Visual Basic usando EdmGen.exe  
  
1. Creare il database School. Per ulteriori informazioni, vedere [Creazione del database di esempio della scuola](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399731(v=vs.100)).  
  
2. Generare il modello School o ottenere il file School.csdl. Per ulteriori informazioni, vedere [Procedura: utilizzare EdmGen.exe per generare i file](how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md)di modello e di mapping .  
  
3. Al prompt dei comandi eseguire il comando seguente senza interruzioni di riga:  
  
    ```console  
    "%windir%\Microsoft.NET\Framework\v4.0.30319\edmgen.exe" /mode:EntityClassGeneration
    /incsdl:.\School.csdl /outobjectlayer:.\School.Objects.vb /language:VB  
    ```  
  
### <a name="to-generate-object-layer-code-for-the-school-model-for-a-c-project-using-edmgenexe"></a>Per generare il codice del livello oggetti per il modello School per un progetto di C# usando EdmGen.exe  
  
1. Creare il database School. Per ulteriori informazioni, vedere [Creazione del database di esempio della scuola](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399731(v=vs.100)).  
  
2. Generare il modello School o ottenere il file School.csdl. Per ulteriori informazioni, vedere [Procedura: utilizzare EdmGen.exe per generare i file](how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md)di modello e di mapping .  
  
3. Al prompt dei comandi eseguire il comando seguente senza interruzioni di riga:  
  
    ```console  
    "%windir%\Microsoft.NET\Framework\v4.0.30319\edmgen.exe" /mode:EntityClassGeneration
    /incsdl:.\School.csdl /outobjectlayer:.\School.Objects.cs /language:CSharp  
    ```  
  
## <a name="see-also"></a>Vedere anche

- [Modellazione e mapping](modeling-and-mapping.md)
- [Procedura: configurare manualmente un progetto Entity Framework](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738546(v=vs.100))
- [Strumenti di ADO.NET Entity Data Model](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399249(v=vs.100))
- [Procedura: pre-generare viste per migliorare le prestazioni di query](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb896240(v=vs.100))
- [Procedura: utilizzare EdmGen.exe per generare i file di modello e di mapping](how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md)
