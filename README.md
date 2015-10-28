# tutoriais-QrCodeGenerator
Codigo fonte de como gerar Qr Codes usando a Lib zXing - android, exemplo simples fácil.
abraco

#How-To


                    QRCodeWriter writer = new QRCodeWriter();

                    try {
                        BitMatrix bitMatrix = writer.encode("21202795", BarcodeFormat.QR_CODE, 512, 512);
                        int width = bitMatrix.getWidth();
                        int height = bitMatrix.getHeight();
                        Bitmap bmp = Bitmap.createBitmap(width, height, Bitmap.Config.RGB_565);
                        for (int x = 0; x < width; x++) {
                            for (int y = 0; y < height; y++) {

                                //pinta a matriz de bitmap com preto ou branco dependendo se existir
                                //ou nao em bitMatrix;
                                bmp.setPixel(x, y, bitMatrix.get(x, y) ? Color.BLACK : Color.WHITE);
                            }
                        }

                        ((ImageView) findViewById(R.id.myQrCode)).setImageBitmap(bmp);

                    } catch (WriterException e) {
                        e.printStackTrace();
                    }



# Dependências:

Nao se esqueca de adicionar a dependencia no seu Gradle app level;

 compile 'com.google.zxing:core:3.2.1'



## Comentarios:

Ruddá Beltrão Lab 312 - Instituto de Ciencias Exatas e Tecnologia Icet - Ufam
