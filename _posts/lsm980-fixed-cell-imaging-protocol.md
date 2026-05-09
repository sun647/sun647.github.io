# LSM980 Protocol: Fixed Cell Imaging

## Setup

1. Turn on the power switch.
2. Login to the session and open **ZEN Blue** software.
3. Calibrate the system.
4. Place the sample on the stage. Make sure the objective lens is at the lowest magnification.

## Sample Finding

1. In ZEN Blue, press **AI Sample Finder**.
2. Click **Next**, check **DAPI**, click **Preview**, then **Finish**.
3. A **Navigation** tab will appear.

## Channel Configuration

1. Go to **Smart Setup**.
2. Add the channels you want to image: **DAPI**, **AF647**, **AF488**.
3. On the left panel of the Acquisition tab, press **+ Widefield** to add a third track called **TL Coherence**.

## Widefield Tile Imaging

1. Check only the **WF** (widefield) track.
2. Check **Tile**.
3. Double-click the area you want to image, then press **Live**.
4. Adjust focus until the image is in focus.
5. Move to the corner of the desired square.
6. Set up by **Contour** — draw a 2×2 square starting at the corner of the desired area. This defines the tile region to be collected.
7. Press **Start Experiment**.
8. Save the image as a **.czi** file.
9. The system will collect a 2×2 tile image of the drawn square.

## Confocal Imaging

1. Uncheck the **WF** track.
2. Check the **confocal** tracks.
3. Press **Live** to adjust focus.
4. Press **Start Experiment**.
5. Save the image as a **.czi** file.

## Moving to a New Area

1. Go back to the **Navigation** tab.
2. Double-click a new area to image and repeat the confocal imaging steps.
