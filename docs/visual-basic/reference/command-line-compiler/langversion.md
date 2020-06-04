---
title: -langversion
ms.date: 03/10/2018
helpviewer_keywords:
- /langversion compiler option [Visual Basic]
- langversion compiler option [Visual Basic]
- -langversion compiler option [Visual Basic]
ms.assetid: 59b7b0c8-2dde-4e9b-94e7-0237f7e0bafb
ms.openlocfilehash: 271606ac021e6afcb28fdac3e1bc86e1aaba7d2b
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84408538"
---
# <a name="-langversion-visual-basic"></a>-langversion (Visual Basic)
Fa in modo che il compilatore accetti solo la sintassi inclusa nella versione della lingua Visual Basic specificata.  
  
## <a name="syntax"></a>Sintassi  
  
```console  
-langversion:version  
```  
  
## <a name="arguments"></a>Argomenti  
 `version`  
 Obbligatorio. La versione del linguaggio da utilizzare durante la compilazione. I valori accettati sono `9` ,, `10` `11` , `12` , `14` , `15` , `15.3` , `15.5` `default` e `latest` .

 I numeri interi possono essere specificati anche usando `.0` come versione secondaria, ad esempio `11.0` .

 È possibile visualizzare l'elenco di tutti i valori possibili specificando `-langversion:?` nella riga di comando.  
  
## <a name="remarks"></a>Commenti  
 L' `-langversion` opzione specifica la sintassi accettata dal compilatore. Se, ad esempio, si specifica che la versione del linguaggio è 9,0, il compilatore genera errori per la sintassi valida solo nella versione 10,0 e successive.  
  
 È possibile utilizzare questa opzione quando si sviluppano applicazioni destinate a versioni diverse del .NET Framework. Ad esempio, se la destinazione è .NET Framework 3,5, è possibile usare questa opzione per assicurarsi di non usare la sintassi della versione 10,0 del linguaggio.  
  
 È possibile impostare `-langversion` direttamente solo tramite la riga di comando. Per ulteriori informazioni, vedere la pagina relativa alla [destinazione di una specifica .NET Framework versione](/visualstudio/ide/visual-studio-multi-targeting-overview).  
  
## <a name="example"></a>Esempio  
 Il codice seguente viene compilato `sample.vb` per Visual Basic 9,0.  
  
```console  
vbc -langversion:9.0 sample.vb  
```  
  
## <a name="see-also"></a>Vedere anche

- [Compilatore della riga di comando di Visual Basic](index.md)
- [Esempi di righe di comando di compilazione](sample-compilation-command-lines.md)
- [Sviluppo per una versione specifica di .NET Framework](/visualstudio/ide/visual-studio-multi-targeting-overview)
