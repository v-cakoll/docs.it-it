---
title: Il file specificato in FileName non è un file XML valido
ms.date: 07/20/2015
ms.assetid: c4c30bf3-e0ad-4bc8-89e0-2c3e49e9793b
ms.openlocfilehash: 89499b07e767bd0b3a777db4e5155f64a4357f0c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "62052313"
---
# <a name="file-specified-in-filename-is-not-a-valid-xml-file"></a>Il file specificato in FileName non è un file XML valido

Il nome file fornito non è un file XML valido. Per specificare la struttura e il contenuto consentito di un documento XML, è possibile usare una definizione DTD (Document Type Definition), uno schema XDR (XML-Data Reduced) o uno schema XSD (XML Schema Definition Language). Gli schemi XSD rappresentano modo migliore per specificare le grammatiche XML in [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)].

> [!NOTE]
> Nelle precedenti versioni di Visual Studio, **Progettazione XML** è la finestra di progettazione per i dataset tipizzati e lo schema XML. È ancora possibile usare **Progettazione XML** per creare e modificare i file di schema XML. Tuttavia, in Visual Studio 2012, la finestra di progettazione per la creazione e modifica di dataset tipizzati è il **Progettazione Dataset**. Per altre informazioni, vedere [creazione e modifica di dataset tipizzati](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/314t4see(v=vs.120)).

## <a name="to-correct-this-error"></a>Per correggere l'errore

- Verificare che il nome file fornito sia corretto.

- Accertarsi che il file specificato contenga XML valido, caricando il file XML che si vuole verificare in **Progettazione XML**. Scegliere **Convalida dati XML** dal menu **XML**. Gli errori sono visualizzati nell' **Elenco attività**.

- Se il file XML ha uno schema XML associato, verificare che gli elementi appaiano nella struttura definita e che il contenuto dei singoli elementi sia conforme ai tipi di dati dichiarati specificati nello schema.

## <a name="see-also"></a>Vedere anche

- <xref:System.Xml>
- [Procedura: Analizzare percorsi di file](../../visual-basic/developing-apps/programming/drives-directories-files/how-to-parse-file-paths.md)