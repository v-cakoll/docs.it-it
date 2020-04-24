---
title: -langversion
ms.date: 03/10/2018
helpviewer_keywords:
- /langversion compiler option [Visual Basic]
- langversion compiler option [Visual Basic]
- -langversion compiler option [Visual Basic]
ms.assetid: 59b7b0c8-2dde-4e9b-94e7-0237f7e0bafb
ms.openlocfilehash: 72a5638a5c5364381ffd68604b0d44830d53f365
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74344205"
---
# <a name="-langversion-visual-basic"></a>-langversion (Visual Basic)
Fa in modo che il compilatore accetti solo la sintassi inclusa nella versione della lingua Visual Basic specificata.  
  
## <a name="syntax"></a>Sintassi  
  
```console  
-langversion:version  
```  
  
## <a name="arguments"></a>Argomenti  
 `version`  
 Obbligatorio. La versione del linguaggio da utilizzare durante la compilazione. `9`I valori accettati `10`sono `11`, `12`, `14`, `15`, `15.3`, `15.5`, `default` , `latest`e.

 I numeri interi possono essere specificati anche usando `.0` come versione secondaria, ad esempio. `11.0`

 È possibile visualizzare l'elenco di tutti i valori possibili specificando `-langversion:?` nella riga di comando.  
  
## <a name="remarks"></a>Osservazioni  
 L' `-langversion` opzione specifica la sintassi accettata dal compilatore. Se, ad esempio, si specifica che la versione del linguaggio è 9,0, il compilatore genera errori per la sintassi valida solo nella versione 10,0 e successive.  
  
 È possibile utilizzare questa opzione quando si sviluppano applicazioni destinate a versioni diverse del .NET Framework. Ad esempio, se la destinazione è .NET Framework 3,5, è possibile usare questa opzione per assicurarsi di non usare la sintassi della versione 10,0 del linguaggio.  
  
 È possibile impostare `-langversion` direttamente solo tramite la riga di comando. Per ulteriori informazioni, vedere la pagina relativa alla [destinazione di una specifica .NET Framework versione](/visualstudio/ide/visual-studio-multi-targeting-overview).  
  
## <a name="example"></a>Esempio  
 Il codice seguente viene compilato `sample.vb` per Visual Basic 9,0.  
  
```console  
vbc -langversion:9.0 sample.vb  
```  
  
## <a name="see-also"></a>Vedi anche

- [Compilatore della riga di comando di Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)
- [Esempi di righe di comando di compilazione](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [Sviluppo per una versione specifica di .NET Framework](/visualstudio/ide/visual-studio-multi-targeting-overview)
