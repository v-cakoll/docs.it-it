---
ms.openlocfilehash: abb89099c4c8a5d9c0e55ef8f357faf44e75b045
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59774215"
---
### <a name="wpf-spell-checking-in-text-enabled-controls-will-not-work-in-windows-10-for-languages-not-in-the-oss-input-language-list"></a>Il controllo ortografico WPF nei controlli con supporto di testo non funziona in Windows 10 per le lingue non incluse nell'elenco lingue di input del sistema operativo

|   |   |
|---|---|
|Dettagli|Durante l'esecuzione in Windows 10, il controllo ortografico potrebbe non funzionare per i controlli WPF basati su testo perché le funzionalità di controllo ortografico della piattaforma sono disponibili solo per le lingue presenti nell'elenco delle lingue di input. In Windows 10, quando una lingua viene aggiunta all'elenco di tastiere disponibili, Windows scarica e installa automaticamente una funzione corrispondente nel pacchetto di funzionalità su richiesta (FOD, Feature on Demand) che offre funzionalità di controllo ortografico. Aggiungendo la lingua all'elenco di lingue di input, il controllo ortografico sarà supportato.|
|Suggerimento|Tenere presente che per il funzionamento del controllo ortografico in Windows 10 è necessario aggiungere la lingua o il testo da sottoporre a controllo come lingua di input.|
|Ambito|Microsoft Edge|
|Versione|4.6|
|Tipo|Runtime|
