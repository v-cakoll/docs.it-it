---
title: -removeintchecks
ms.date: 03/13/2018
f1_keywords:
- removeintchecks
- -removeintchecks
helpviewer_keywords:
- removeintchecks compiler option [Visual Basic]
- /removeintchecks compiler option [Visual Basic]
- -removeintchecks compiler option [Visual Basic]
ms.assetid: c1835bd5-1e38-4fba-bd2f-6984774765d4
ms.openlocfilehash: bea6ca24ea6da9000267e754d52fe0ca152f7d7f
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/07/2019
ms.locfileid: "72005235"
---
# <a name="-removeintchecks"></a>-removeintchecks
Attiva o disattiva il controllo degli errori di overflow per le operazioni integer.  
  
## <a name="syntax"></a>Sintassi  
  
```console  
-removeintchecks[+ | -]  
```  
  
## <a name="arguments"></a>Argomenti  
  
|Nome|Definizione|  
|---|---|  
|`+` &#124; `-`|facoltativo. L'opzione `-removeintchecks-` induce il compilatore a controllare tutti i calcoli Integer per rilevare errori di overflow. Il valore predefinito è `-removeintchecks-`.<br /><br /> Se si specifica `-removeintchecks` o `-removeintchecks+`, il controllo degli errori e i calcoli Integer possono essere più veloci. Tuttavia, senza il controllo degli errori e in caso di overflow delle capacità del tipo di dati, i risultati non corretti possono essere archiviati senza generare un errore.|  
  
|Per impostare-removeintchecks (in Visual Studio Integrated Development Environment|  
|---|  
|1.  Selezionare un progetto in **Esplora soluzioni**. Scegliere **Proprietà** dal menu **Progetto**. <br />2.  Fare clic sulla scheda **Compila**.<br />3.  Fare clic su **Avanzate** .<br />4.  Modificare il valore della casella di **controllo Rimuovi overflow di Integer** .|  
  
## <a name="example"></a>Esempio  
 Il codice seguente compila `Test.vb` e disattiva il controllo degli errori di overflow di Integer.  
  
```console
vbc -removeintchecks+ test.vb  
```  
  
## <a name="see-also"></a>Vedere anche

- [Compilatore della riga di comando di Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)
- [Esempi di righe di comando di compilazione](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
