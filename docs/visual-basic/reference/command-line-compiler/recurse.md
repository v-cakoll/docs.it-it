---
title: -recurse
ms.date: 03/13/2018
helpviewer_keywords:
- /recurse compiler option [Visual Basic]
- -recurse compiler option [Visual Basic]
- recurse compiler option [Visual Basic]
ms.assetid: 84a0b670-33ae-44c4-a46a-b90388809317
ms.openlocfilehash: fc8dfe41ea56531ff34cd5e551ef24d636227e47
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84400500"
---
# <a name="-recurse"></a>-recurse
Compila i file del codice sorgente in tutte le directory figlio della directory specificata o della directory del progetto.  
  
## <a name="syntax"></a>Sintassi  
  
```console  
-recurse:[dir\]file  
```  
  
## <a name="arguments"></a>Argomenti  
 `dir`  
 Facoltativa. La directory in cui si vuole che abbia inizio la ricerca. Se non specificato, la ricerca inizia nella directory del progetto.  
  
 `file`  
 Obbligatorio. I file da cercare. È consentito l'utilizzo di caratteri jolly.  
  
## <a name="remarks"></a>Commenti  
 È possibile usare caratteri jolly in un nome file per compilare tutti i file corrispondenti nella directory del progetto senza usare `-recurse` . Se non viene specificato alcun nome file di output, il compilatore basa il nome del file di output sul primo file di input elaborato. Si tratta in genere del primo file nell'elenco di file compilato quando viene visualizzato in ordine alfabetico. Per questo motivo, è preferibile specificare un file di output usando l' `-out` opzione.  
  
> [!NOTE]
> L' `-recurse` opzione non è disponibile nell'ambiente di sviluppo di Visual Studio. è disponibile solo quando si esegue la compilazione dalla riga di comando.  
  
## <a name="example"></a>Esempio  
 Il comando seguente compila tutti i file di Visual Basic nella directory corrente.  
  
```console
vbc *.vb  
```  
  
 Il comando seguente compila tutti i file di Visual Basic nella `Test\ABC` Directory e in tutte le directory sottostanti, quindi genera `Test.ABC.dll` .  
  
```console
vbc -target:library -out:Test.ABC.dll -recurse:Test\ABC\*.vb  
```  
  
## <a name="see-also"></a>Vedere anche

- [Compilatore della riga di comando di Visual Basic](index.md)
- [-out (Visual Basic)](out.md)
- [Esempi di righe di comando di compilazione](sample-compilation-command-lines.md)
