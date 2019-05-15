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
ms.openlocfilehash: e8dfe95ef3385635f5839ecc96047911544a256e
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/14/2019
ms.locfileid: "65591445"
---
# <a name="-baseaddress"></a>-baseaddress
Specifica un indirizzo di base predefinito durante la creazione di una DLL.  
  
## <a name="syntax"></a>Sintassi  
  
```  
-baseaddress:address  
```  
  
## <a name="arguments"></a>Argomenti  
  
|Termine|Definizione|  
|---|---|  
|`address`|Obbligatorio. Indirizzo di base per la DLL. Questo indirizzo deve essere specificato come numero esadecimale.|  
  
## <a name="remarks"></a>Note  
 L'indirizzo di base predefinito per una DLL è impostata da .NET Framework.  
  
 Tenere presente che la parola di ordine inferiore di questo indirizzo viene arrotondata. Ad esempio, se si specifica 0x11110001, il valore viene arrotondato a 0x11110000.  
  
 Per completare il processo di firma per una DLL, usare il `–R` opzione dello strumento nome sicuro (Sn.exe).  
  
 Questa opzione viene ignorata se la destinazione non è una DLL.  
  
|Per impostare - baseaddress nell'IDE di Visual Studio|  
|---|  
|1.  Selezionare un progetto in **Esplora soluzioni**. Scegliere **Proprietà** dal menu **Progetto**. <br />2.  Fare clic sulla scheda **Compila**.<br />3.  Scegliere **Avanzate**.<br />4.  Modificare il valore di **indirizzo di base DLL:** casella. **Nota:**      Il **indirizzo di base DLL:** casella è di sola lettura, a meno che la destinazione è una DLL.|  
  
## <a name="see-also"></a>Vedere anche

- [Compilatore della riga di comando di Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)
- [-target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md)
- [Esempi di righe di comando di compilazione](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [Sn.exe (strumento nome sicuro)](../../../framework/tools/sn-exe-strong-name-tool.md))
