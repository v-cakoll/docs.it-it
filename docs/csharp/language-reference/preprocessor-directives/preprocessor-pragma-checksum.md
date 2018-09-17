---
title: '#pragma checksum (Riferimenti per C#)'
ms.date: 07/20/2015
f1_keywords:
- '#pragma checksum'
helpviewer_keywords:
- '#pragma checksum [C#]'
ms.assetid: 3673e4ca-6098-4ec1-890f-8fceb2a794a2
ms.openlocfilehash: 28a9ccfb9d36e648304a177294904ab1b7f18892
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/17/2018
ms.locfileid: "45614504"
---
# <a name="pragma-checksum-c-reference"></a>#pragma checksum (Riferimenti per C#)
Consente di generare i checksum per i file di origine facilitando in tal modo le operazioni di debug delle pagine [!INCLUDE[vstecasp](~/includes/vstecasp-md.md)].  
  
## <a name="syntax"></a>Sintassi  
  
```csharp
#pragma checksum "filename" "{guid}" "checksum bytes"  
```  
  
#### <a name="parameters"></a>Parametri  
 `"filename"`  
 Nome del file che richiede il monitoraggio per modifiche o aggiornamenti.  
  
 `"{guid}"`  
 Identificatore univoco globale (GUID, Globally Unique Identifier) dell'algoritmo hash.  
  
 `"checksum_bytes"`  
 Stringa di cifre esadecimali che rappresenta i byte del checksum. Deve essere un numero pari di cifre esadecimali. Un numero dispari di cifre genera un avviso in fase di compilazione, pertanto la direttiva viene ignorata.  
  
## <a name="remarks"></a>Note  
 Il debugger di Visual Studio usa un checksum per trovare sempre l'origine corretta. Il compilatore calcola il checksum di un file di origine, quindi genera l'output nel file del database di programma (PDB). Il PDB viene quindi usato dal debugger per eseguire il confronto con il checksum calcolato per il file di origine.  
  
 Questa soluzione non funziona per i progetti [!INCLUDE[vstecasp](~/includes/vstecasp-md.md)] ASP.NET, poiché il checksum calcolato si riferisce al file di origine generato piuttosto che al file ASPX. Per risolvere questo problema, `#pragma checksum` fornisce supporto per il checksum nelle pagine [!INCLUDE[vstecasp](~/includes/vstecasp-md.md)].  
  
 Quando si crea un progetto [!INCLUDE[vstecasp](~/includes/vstecasp-md.md)] in Visual C#, il file di origine generato contiene un checksum per il file ASPX, dal quale viene generata l'origine. Queste informazioni vengono quindi scritte dal compilatore nel file PDB.  
  
 Se il compilatore non rileva alcuna direttiva `#pragma checksum` nel file, calcola il checksum e scrive il valore nel file PDB.  
  
## <a name="example"></a>Esempio  
  
```csharp
class TestClass  
{  
    static int Main()  
    {  
        #pragma checksum "file.cs" "{406EA660-64CF-4C82-B6F0-42D48172A799}" "ab007f1d23d9" // New checksum  
    }  
}  
```  
  
## <a name="see-also"></a>Vedere anche

- [Riferimenti per C#](../../../csharp/language-reference/index.md)  
- [Guida per programmatori C#](../../../csharp/programming-guide/index.md)  
- [Direttive per il preprocessore C#](../../../csharp/language-reference/preprocessor-directives/index.md)
