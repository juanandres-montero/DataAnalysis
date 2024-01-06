{
  "nbformat": 4,
  "nbformat_minor": 0,
  "metadata": {
    "colab": {
      "provenance": [],
      "authorship_tag": "ABX9TyO8Vt4MqI7c+m4hc/NCG/ED",
      "include_colab_link": true
    },
    "kernelspec": {
      "name": "python3",
      "display_name": "Python 3"
    },
    "language_info": {
      "name": "python"
    }
  },
  "cells": [
    {
      "cell_type": "markdown",
      "metadata": {
        "id": "view-in-github",
        "colab_type": "text"
      },
      "source": [
        "<a href=\"https://colab.research.google.com/github/juanandres-montero/DataAnalysis/blob/main/Obtener_datos_del_TSE_por_cedulas.ipynb\" target=\"_parent\"><img src=\"https://colab.research.google.com/assets/colab-badge.svg\" alt=\"Open In Colab\"/></a>"
      ]
    },
    {
      "cell_type": "code",
      "source": [
        "#@markdown # Instalar requerimientos\n",
        "!pip install selenium\n",
        "!apt-get update # to update ubuntu to correctly run apt install\n",
        "!apt install chromium-chromedriver\n",
        "!cp /usr/lib/chromium-browser/chromedriver /usr/bin\n",
        "!pip install webdriver_manager\n",
        "import sys\n",
        "sys.path.insert(0,'/usr/lib/chromium-browser/chromedriver')\n",
        "from selenium import webdriver\n",
        "from webdriver_manager.chrome import ChromeDriverManager\n",
        "import pandas as pd\n",
        "from google.colab import files"
      ],
      "metadata": {
        "cellView": "form",
        "id": "qjWtLB2dOeDr"
      },
      "execution_count": null,
      "outputs": []
    },
    {
      "cell_type": "code",
      "source": [
        "import time\n",
        "from google.colab import files\n",
        "def get_info(cedula):\n",
        "  options = webdriver.ChromeOptions()\n",
        "  options.add_argument('--headless')\n",
        "  options.add_argument('--no-sandbox')\n",
        "  options.add_argument('--disable-dev-shm-usage')\n",
        "  driver = webdriver.Chrome(options=options)\n",
        "  driver.get('https://servicioselectorales.tse.go.cr/chc/consulta_cedula.aspx')\n",
        "  # Enter the cedula number\n",
        "  box = driver.find_element('xpath','//*[@id=\"txtcedula\"]')\n",
        "  box.send_keys(cedula)\n",
        "  driver.find_element('xpath','//*[@id=\"btnConsultaCedula\"]').click()\n",
        "  time.sleep(1)\n",
        "  driver.find_element('xpath','//*[@id=\"LinkButton11\"]').click()\n",
        "  time.sleep(1)\n",
        "  table = driver.find_element('xpath', '//*[@id=\"form1\"]/table[2]')\n",
        "  rows = table.find_elements('xpath','//*[@id=\"form1\"]/table[2]/tbody/tr')\n",
        "  df = pd.read_html(table.get_attribute('outerHTML'))\n",
        "  driver.find_element('xpath','//*[@id=\"ImageConsultaCedula\"]').click()\n",
        "  time.sleep(1)\n",
        "  return df\n",
        "\n",
        "def format(df):\n",
        "  df_transposed = df.transpose()\n",
        "  f0 = df_transposed.iloc[[0]]\n",
        "  f1 = df_transposed.iloc[[1]]\n",
        "  f2 = df_transposed.iloc[[2]]\n",
        "  f3 = df_transposed.iloc[[3]]\n",
        "  df0 = pd.concat([f0, f1], axis=0)\n",
        "  df1 = pd.concat([f2, f3], axis=0)\n",
        "  df1 = df1.reset_index()\n",
        "  new_df = pd.concat([df0, df1], axis=1)\n",
        "  new_df = new_df.drop(columns=['index'])\n",
        "  new_df.columns = new_df.iloc[0]\n",
        "  new_df = new_df.drop(0)\n",
        "  new_df = new_df.dropna(axis=1, how='all')\n",
        "  return new_df\n",
        "#@markdown - Ingrese los números de cédula separados por comas sin espacios\n",
        "def main():\n",
        "  Numeros_de_cedulas = \"105600795\" #@param {type:\"string\"}\n",
        "  cedulas = (Numeros_de_cedulas).split(',')\n",
        "  df = pd.DataFrame()\n",
        "  data = pd.DataFrame()\n",
        "  save = pd.DataFrame()\n",
        "  for cedula in cedulas:\n",
        "    try:\n",
        "      df = df.append(get_info(cedula))\n",
        "      data = data.append(format(df))\n",
        "      save = save.append(data)\n",
        "\n",
        "      data = pd.DataFrame()\n",
        "      df = pd.DataFrame()\n",
        "    except:\n",
        "      print('Error: Invalid cedula number')\n",
        "    # Reformatear y organizar los datos\n",
        "  print(save)\n",
        "  save.to_excel(\"data_export.xlsx\", sheet_name=\"Sheet1\")\n",
        "  files.download(\"data_export.xlsx\")\n",
        "\n",
        "if __name__ == '__main__':\n",
        "  main()\n",
        "#@markdown Los datos del TSE de las cédulas se exportarán automáticamente en formato excel."
      ],
      "metadata": {
        "colab": {
          "base_uri": "https://localhost:8080/",
          "height": 364
        },
        "cellView": "form",
        "id": "air2AB1_T7UR",
        "outputId": "ebd32705-f07e-4a82-e120-e533e8781e06"
      },
      "execution_count": null,
      "outputs": [
        {
          "output_type": "stream",
          "name": "stdout",
          "text": [
            "0 Número de Cédula:                   Nombre: Primer Apellido:  \\\n",
            "1         105600795  RODRIGO ALBERTO DE JESUS           CHAVES   \n",
            "\n",
            "0 Segundo Apellido: Fecha de Nacimiento:        Lugar de Nacimiento:  \\\n",
            "1            ROBLES           10/06/1961  EL CARMEN CENTRAL SAN JOSE   \n",
            "\n",
            "0  Nacionalidad:               Hijo/a de: Identificación:  \\\n",
            "1  COSTARRICENSE  RODRIGO CHAVES ARGUEDAS               0   \n",
            "\n",
            "0                     Y: Identificación: Empadronado/a: Fallecido/a:  \\\n",
            "1  ALICIA ROBLES JIMENEZ       102140104             SI           NO   \n",
            "\n",
            "0 Marginal:      Sexo:  \n",
            "1        NO  MASCULINO  \n"
          ]
        },
        {
          "output_type": "stream",
          "name": "stderr",
          "text": [
            "<ipython-input-125-bbf3085306bb>:48: FutureWarning: The frame.append method is deprecated and will be removed from pandas in a future version. Use pandas.concat instead.\n",
            "  df = df.append(get_info(cedula))\n",
            "<ipython-input-125-bbf3085306bb>:49: FutureWarning: The frame.append method is deprecated and will be removed from pandas in a future version. Use pandas.concat instead.\n",
            "  data = data.append(format(df))\n",
            "<ipython-input-125-bbf3085306bb>:50: FutureWarning: The frame.append method is deprecated and will be removed from pandas in a future version. Use pandas.concat instead.\n",
            "  save = save.append(data)\n"
          ]
        },
        {
          "output_type": "display_data",
          "data": {
            "text/plain": [
              "<IPython.core.display.Javascript object>"
            ],
            "application/javascript": [
              "\n",
              "    async function download(id, filename, size) {\n",
              "      if (!google.colab.kernel.accessAllowed) {\n",
              "        return;\n",
              "      }\n",
              "      const div = document.createElement('div');\n",
              "      const label = document.createElement('label');\n",
              "      label.textContent = `Downloading \"${filename}\": `;\n",
              "      div.appendChild(label);\n",
              "      const progress = document.createElement('progress');\n",
              "      progress.max = size;\n",
              "      div.appendChild(progress);\n",
              "      document.body.appendChild(div);\n",
              "\n",
              "      const buffers = [];\n",
              "      let downloaded = 0;\n",
              "\n",
              "      const channel = await google.colab.kernel.comms.open(id);\n",
              "      // Send a message to notify the kernel that we're ready.\n",
              "      channel.send({})\n",
              "\n",
              "      for await (const message of channel.messages) {\n",
              "        // Send a message to notify the kernel that we're ready.\n",
              "        channel.send({})\n",
              "        if (message.buffers) {\n",
              "          for (const buffer of message.buffers) {\n",
              "            buffers.push(buffer);\n",
              "            downloaded += buffer.byteLength;\n",
              "            progress.value = downloaded;\n",
              "          }\n",
              "        }\n",
              "      }\n",
              "      const blob = new Blob(buffers, {type: 'application/binary'});\n",
              "      const a = document.createElement('a');\n",
              "      a.href = window.URL.createObjectURL(blob);\n",
              "      a.download = filename;\n",
              "      div.appendChild(a);\n",
              "      a.click();\n",
              "      div.remove();\n",
              "    }\n",
              "  "
            ]
          },
          "metadata": {}
        },
        {
          "output_type": "display_data",
          "data": {
            "text/plain": [
              "<IPython.core.display.Javascript object>"
            ],
            "application/javascript": [
              "download(\"download_51adc144-80fb-4a52-96b8-3b8ad5bd0679\", \"data_export.xlsx\", 5281)"
            ]
          },
          "metadata": {}
        }
      ]
    }
  ]
}
