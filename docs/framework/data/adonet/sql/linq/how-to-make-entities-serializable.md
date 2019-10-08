---
title: 'Procedura: Rendere serializzabili le entità'
ms.date: 03/30/2017
ms.assetid: a6c5bf6e-064a-4f77-b74c-76b3a5dec309
ms.openlocfilehash: 5e9d078ed2daacfa48b09693f533e9aade613281
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/07/2019
ms.locfileid: "72002705"
---
# <a name="how-to-make-entities-serializable"></a>Procedura: Rendere serializzabili le entità
Quando si genera il codice, è possibile rendere serializzabili le entità. Le classi di entità vengono decorate con l'attributo <xref:System.Runtime.Serialization.DataContractAttribute> e le colonne con l'attributo <xref:System.Runtime.Serialization.DataMemberAttribute>.  
  
 Gli sviluppatori che usano Visual Studio possono usare la Object Relational Designer a questo scopo.  
  
 Se si utilizza lo strumento da riga di comando SQLMetal, utilizzare l'opzione **/Serialization** con l'argomento `unidirectional`. Per altre informazioni, vedere [SqlMetal.exe (strumento per la generazione del codice)](../../../../tools/sqlmetal-exe-code-generation-tool.md).  
  
## <a name="example"></a>Esempio  
 Le righe di comando SQLMetal seguenti consentono di produrre file con entità serializzabili.  
  
```console  
sqlmetal /code:nwserializable.vb /language:vb "c:\northwnd.mdf" /sprocs /functions /pluralize /serialization:unidirectional  
```  
  
```console  
sqlmetal /code:nwserializable.cs /language:csharp "c:\northwnd.mdf" /sprocs /functions /pluralize /serialization:unidirectional  
```  
  
## <a name="see-also"></a>Vedere anche

- [Serializzazione](serialization.md)
- [Creazione del modello a oggetti](creating-the-object-model.md)
