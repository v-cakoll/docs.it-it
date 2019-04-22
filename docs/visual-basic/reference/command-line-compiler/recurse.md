---
title: -recurse
ms.date: 03/13/2018
helpviewer_keywords:
- /recurse compiler option [Visual Basic]
- -recurse compiler option [Visual Basic]
- recurse compiler option [Visual Basic]
ms.assetid: 84a0b670-33ae-44c4-a46a-b90388809317
ms.openlocfilehash: 2fe1834c3e92c3eff016ffd7857a0473eb2e8b3a
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "58816421"
---
# <a name="-recurse"></a>-recurse
Compila i file di codice sorgente in tutte le directory figlio della directory specificata o della directory del progetto.  
  
## <a name="syntax"></a>Sintassi  
  
```  
-recurse:[dir\]file  
```  
  
## <a name="arguments"></a>Argomenti  
 `dir`  
 Facoltativo. La directory in cui si vuole che abbia inizio la ricerca. Se non specificato, la ricerca inizia nella directory del progetto.  
  
 `file`  
 Obbligatorio. I file da cercare. È consentito l'utilizzo di caratteri jolly.  
  
## <a name="remarks"></a>Note  
 È possibile usare caratteri jolly in un nome file per compilare tutti i file corrispondenti nella directory del progetto senza usare `-recurse`. Se viene specificato alcun nome di file di output, il compilatore si basa il nome del file di output nel primo file di input elaborato. Si tratta in genere il primo file nell'elenco dei file compilati quando viene visualizzato in ordine alfabetico. Per questo motivo, è consigliabile specificare un file di output usando il `-out` opzione.  
  
> [!NOTE]
>  Il `-recurse` opzione non è disponibile all'interno dell'ambiente di sviluppo di Visual Studio, è disponibile solo durante la compilazione dalla riga di comando.  
  
## <a name="example"></a>Esempio  
 Il comando seguente compila tutti i file di Visual Basic nella directory corrente.  
  
```console
vbc *.vb  
```  
  
 Il comando seguente compila tutti i file Visual Basic il `Test\ABC` directory e qualsiasi directory sotto di essa, quindi genera `Test.ABC.dll`.  
  
```console
vbc -target:library -out:Test.ABC.dll -recurse:Test\ABC\*.vb  
```  
  
## <a name="see-also"></a>Vedere anche

- [Compilatore della riga di comando di Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)
- [-out (Visual Basic)](../../../visual-basic/reference/command-line-compiler/out.md)
- [Esempi di righe di comando di compilazione](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
