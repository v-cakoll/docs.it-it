---
title: -reference
ms.date: 03/13/2018
helpviewer_keywords:
- /reference compiler option [Visual Basic]
- r compiler option [Visual Basic]
- -reference compiler option [Visual Basic]
- /r compiler option [Visual Basic]
- reference compiler option [Visual Basic]
- -r compiler option [Visual Basic]
ms.assetid: 66bdfced-bbf6-43d1-a554-bc0990315737
ms.openlocfilehash: 633b457106203e213f5d30003e576b7e8132f4d2
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84400487"
---
# <a name="-reference-visual-basic"></a>-Reference (Visual Basic)
Fa in modo che il compilatore renda le informazioni sul tipo negli assembly specificati disponibili per il progetto attualmente in fase di compilazione.  
  
## <a name="syntax"></a>Sintassi  
  
```console  
-reference:fileList  
```

Oppure

```console
-r:fileList  
```  
  
## <a name="arguments"></a>Argomenti  
  
|Termine|Definizione|  
|---|---|  
|`fileList`|Obbligatorio. Elenco di nomi di file di assembly delimitato da virgole. Se il nome del file contiene uno spazio, racchiudere il nome tra virgolette.|  
  
## <a name="remarks"></a>Commenti  
 I file importati devono contenere i metadati dell'assembly. Solo i tipi pubblici sono visibili all'esterno dell'assembly. L'opzione [-addmodule](addmodule.md) importa i metadati da un modulo.  
  
 Se si fa riferimento a un assembly (assembly A) che a sua volta fa riferimento a un altro assembly (assembly B), è necessario fare riferimento all'assembly B se:  
  
- Un tipo dell'assembly A eredita da un tipo o implementa un'interfaccia dall'assembly B.  
  
- Viene richiamato un campo, una proprietà, un evento o un metodo che presenta un tipo restituito o un tipo di parametro proveniente dall'assembly B.  
  
 Usare [-LIBPATH](libpath.md) per specificare la directory in cui si trova uno o più riferimenti ad assembly.  
  
 Affinché il compilatore riconosca un tipo in un assembly (non un modulo), è necessario forzare la risoluzione del tipo. Un esempio di come è possibile eseguire questa operazione consiste nel definire un'istanza del tipo. Sono disponibili altri modi per risolvere i nomi dei tipi in un assembly per il compilatore. Se, ad esempio, si eredita da un tipo in un assembly, il nome del tipo diventa noto al compilatore.  
  
 Per impostazione predefinita, viene usato il file di risposta vbc. rsp, che fa riferimento a assembly .NET Framework di uso comune. Usare `-noconfig` se non si vuole che il compilatore usi vbc. rsp.  
  
 La forma breve di `-reference` è `-r`.  
  
## <a name="example"></a>Esempio  
 Il comando seguente compila il file di origine `Input.vb` e gli assembly di riferimento da `Metad1.dll` e `Metad2.dll` per produrre `Out.exe` .  
  
```console
vbc -reference:metad1.dll,metad2.dll -out:out.exe input.vb  
```  
  
## <a name="see-also"></a>Vedere anche

- [Compilatore della riga di comando di Visual Basic](index.md)
- [-noconfig](noconfig.md)
- [-target (Visual Basic)](target.md)
- [Pubblica](../../language-reference/modifiers/public.md)
- [Esempi di righe di comando di compilazione](sample-compilation-command-lines.md)
