---
title: -baseaddress
ms.date: 08/09/2018
f1_keywords:
- /baseaddress
- baseaddress
helpviewer_keywords:
- -baseaddress compiler option [Visual Basic]
- /baseaddress compiler option [Visual Basic]
- baseaddress compiler option [Visual Basic]
ms.assetid: c982bcf2-46e5-47a2-bc8f-a5cc32b7dc47
ms.openlocfilehash: d241584195da7d6f74b45b191c4f63204c200d45
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84357180"
---
# <a name="-baseaddress"></a>-baseaddress
Specifica un indirizzo di base predefinito durante la creazione di una DLL.  
  
## <a name="syntax"></a>Sintassi  
  
```console  
-baseaddress:address  
```  
  
## <a name="arguments"></a>Argomenti  
  
|Termine|Definizione|  
|---|---|  
|`address`|Obbligatorio. Indirizzo di base per la DLL. Questo indirizzo deve essere specificato come numero esadecimale.|  
  
## <a name="remarks"></a>Commenti  
 L'indirizzo di base predefinito per una DLL viene impostato dal .NET Framework.  
  
 Tenere presente che la parola di ordine inferiore in questo indirizzo viene arrotondata. Se ad esempio si specifica 0x11110001, viene arrotondato a 0x11110000.  
  
 Per completare il processo di firma di una DLL, utilizzare l' `–R` opzione dello strumento per la denominazione sicura (sn. exe).  
  
 Questa opzione viene ignorata se la destinazione non è una DLL.  
  
|Per impostare-baseaddress nell'IDE di Visual Studio|  
|---|  
|1. è stato selezionato un progetto in **Esplora soluzioni**. Scegliere **Proprietà** dal menu **Progetto**. <br />2. fare clic sulla scheda **Compila** .<br />3. fare clic su **Avanzate**.<br />4. modificare il valore nella casella **indirizzo di base dll:** . **Nota:**      **Indirizzo di base dll:** box è di sola lettura, a meno che la destinazione non sia una dll.|  
  
## <a name="see-also"></a>Vedere anche

- [Compilatore della riga di comando di Visual Basic](index.md)
- [-target (Visual Basic)](target.md)
- [Esempi di righe di comando di compilazione](sample-compilation-command-lines.md)
- [Sn. exe (strumento nome sicuro)](../../../framework/tools/sn-exe-strong-name-tool.md)
