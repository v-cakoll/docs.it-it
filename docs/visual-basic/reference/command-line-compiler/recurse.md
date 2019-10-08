---
title: -recurse
ms.date: 03/13/2018
helpviewer_keywords:
- /recurse compiler option [Visual Basic]
- -recurse compiler option [Visual Basic]
- recurse compiler option [Visual Basic]
ms.assetid: 84a0b670-33ae-44c4-a46a-b90388809317
ms.openlocfilehash: 71613af0f1c319801296180d49dbacfedf0ceca4
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/07/2019
ms.locfileid: "72005254"
---
# <a name="-recurse"></a>-recurse
Compila i file del codice sorgente in tutte le directory figlio della directory specificata o della directory del progetto.  
  
## <a name="syntax"></a>Sintassi  
  
```console  
-recurse:[dir\]file  
```  
  
## <a name="arguments"></a>Argomenti  
 `dir`  
 facoltativo. La directory in cui si vuole che abbia inizio la ricerca. Se non specificato, la ricerca inizia nella directory del progetto.  
  
 `file`  
 Obbligatorio. I file da cercare. È consentito l'utilizzo di caratteri jolly.  
  
## <a name="remarks"></a>Note  
 È possibile usare caratteri jolly in un nome file per compilare tutti i file corrispondenti nella directory del progetto senza usare `-recurse`. Se non viene specificato alcun nome file di output, il compilatore basa il nome del file di output sul primo file di input elaborato. Si tratta in genere del primo file nell'elenco di file compilato quando viene visualizzato in ordine alfabetico. Per questo motivo, è preferibile specificare un file di output usando l'opzione `-out`.  
  
> [!NOTE]
> L'opzione `-recurse` non è disponibile nell'ambiente di sviluppo di Visual Studio. è disponibile solo quando si esegue la compilazione dalla riga di comando.  
  
## <a name="example"></a>Esempio  
 Il comando seguente compila tutti i file di Visual Basic nella directory corrente.  
  
```console
vbc *.vb  
```  
  
 Il comando seguente compila tutti i file di Visual Basic nella directory `Test\ABC` e in tutte le directory sottostanti, quindi genera `Test.ABC.dll`.  
  
```console
vbc -target:library -out:Test.ABC.dll -recurse:Test\ABC\*.vb  
```  
  
## <a name="see-also"></a>Vedere anche

- [Compilatore della riga di comando di Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)
- [-out (Visual Basic)](../../../visual-basic/reference/command-line-compiler/out.md)
- [Esempi di righe di comando di compilazione](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
