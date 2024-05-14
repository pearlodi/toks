<template>
  <div class="px-8 mt-4 pb-1 border-b-2 border-gray-200 overflow-y-scroll scroll-bar">
    <div class="flex">
      <div class="flex">
        <div class="w-full md:w-[100px]">
          <div class="flex">
            <div class="">
              <p class="text-[gray] text-[8px]">Group by</p>
            </div>
            <div class="w-3 self-end justify-end">
              <img
                src="../assets/images/down-arrow.png"
                alt="search icon"
                class="w-full ml-1"
              />
            </div>
          </div>
          <div class="w-[20px] mt-2">
            <img src="../assets/images/layout.png" alt="copy" class="w-full" />
          </div>
          <div class="flex mt-2">
            <div class="flex items-center">
              <div class="w-[20px]">
                <img
                  src="../assets/images/file.png"
                  alt="copy"
                  class="w-full"
                />
              </div>
              <div>
                <p class="text-[gray] text-[8px] w-[60px] ml-2">
                  Use First Row as Headers
                </p>
              </div>
              <div class="w-3">
                <img
                  src="../assets/images/down-arrow.png"
                  alt="search icon"
                  class="w-full"
                />
              </div>
            </div>
          </div>
        </div>

        <div class="ml-4">
          <div class="flex items-center">
            <div class="w-[20px]">
              <img src="../assets/images/send.png" alt="copy" class="w-full" />
            </div>
            <p class="text-[gray] text-[8px] w-[15px]">Transpose</p>
          </div>

          <div class="flex items-center mt-2">
            <div class="w-[20px]">
              <img
                src="../assets/images/history.png"
                alt="copy"
                class="w-full"
              />
            </div>
            <p class="text-[gray] text-[8px] w-[50px]">Reverse Rows</p>
          </div>

          <div class="flex items-center mt-2">
            <div class="w-[20px]">
              <img
                src="../assets/images/file-and-folder.png"
                alt="copy"
                class="w-full"
              />
            </div>
            <p class="text-[gray] text-[8px] w-[45px]">Count Rows</p>
          </div>
        </div>
      </div>
      <div class="bg-[#80808053] ml-2 w-[1px] h-[60px]"></div>
      <div class="ml-3 flex">
        <div>
          <div class="flex items-center">
            <div class="w-[20px]">
              <img
                src="../assets/images/database-table.png"
                alt="copy"
                class="w-full"
              />
            </div>
            <p class="text-[gray] text-[8px] w-full max-w-full md:w-[60px] ml-1">Data Type: Text</p>
          </div>

          <div class="flex items-center mt-2">
            <div class="w-[20px]">
              <img
                src="../assets/images/clipboard.png"
                alt="copy"
                class="w-full max-w-full"
              />
            </div>
            <p class="text-[gray] text-[8px] w-full max-w-full md:w-[72px]">Detect Data Type</p>
          </div>

          <div class="flex items-center mt-2">
            <div class="w-[20px]">
              <img
                src="../assets/images/rename-file.png"
                alt="copy"
                class="w-full max-w-full"
              />
            </div>
            <p class="text-[gray] text-[8px] w-full max-w-full md:w-[32px]">Rename</p>
          </div>
        </div>
        <div class="ml-2">
          <div class="flex items-center">
            <div class="w-[20px]">
              <img
                src="../assets/images/previous.png"
                alt="copy"
                class="w-full max-w-full"
              />
            </div>
            <div>
              <p class="text-[gray] text-[8px] w-full max-w-full md:w-[59px] ml-1">Replace Values</p>
            </div>
            <div class="w-4">
              <img
                src="../assets/images/down-arrow.png"
                alt="seacrh icon"
                class="w-full max-w-full ml-1"
              />
            </div>
          </div>
          <div class="flex items-center mt-2">
            <div class="w-[20px]">
              <img src="../assets/images/color.png" alt="copy" class="w-full max-w-full" />
            </div>
            <div>
              <p class="text-[gray] text-[8px] w-full max-w-full md:w-[12px] ml-1">Fill</p>
            </div>
          </div>
          <div class="flex items-center mt-2">
            <div class="w-[17px]">
              <img
                src="../assets/images/columns.png"
                alt="copy"
                class="w-full max-w-full"
              />
            </div>
            <div>
              <p class="text-[gray] text-[8px] w-fll max-w-full md:w-[53px] ml-1">Pivot Column</p>
            </div>
          </div>
        </div>
        <div class="ml-2">
          <div class="flex items-center">
            <div class="w-[17px]">
              <img
                src="../assets/images/columns.png"
                alt="copy"
                class="w-full"
              />
            </div>
            <div>
              <p class="text-[gray] text-[8px] w-full max-w-full md:w-[68px] ml-1">
                Unpivot Columns
              </p>
            </div>
            <div class="w-4">
              <img
                src="../assets/images/down-arrow.png"
                alt="seacrh icon"
                class="w-full"
              />
            </div>
          </div>
          <div class="flex items-center mt-2">
            <div class="w-[17px]">
              <img
                src="../assets/images/letter-t.png"
                alt="copy"
                class="w-full"
              />
            </div>
            <div>
              <p class="text-[gray] text-[8px] w-full max-w-full md:w-[22px] ml-1">Move</p>
            </div>
          </div>
          <div class="flex items-center mt-2">
            <div class="w-[17px]">
              <img
                src="../assets/images/number.png"
                alt="copy"
                class="w-full"
              />
            </div>
            <div>
              <p class="text-[gray] text-[8px] w-full max-w-full md:w-[59px] ml-1">
                Convert to List
              </p>
            </div>
          </div>
        </div>
      </div>
      <div class="bg-[#80808053] ml-2 w-[1px] h-[60px]"></div>
      <div class="ml-3 flex items-center">
        <div>
          <div class="mt-2 w-8 flex flex-col justify-center items-center">
            <div class="w-[20px]">
              <img src="../assets/images/split.png" alt="copy" class="w-full" />
            </div>
            <div>
              <p class="text-[gray] text-[8px] text-center w-full max-wfull md:w-[24px] ml-1">
                Split Column
              </p>
            </div>
          </div>
        </div>
        <div class="ml-2">
          <div class="mt-2 w-8 flex flex-col justify-center items-center">
            <div class="w-[24px]">
              <img
                src="../assets/images/file-setting.png"
                alt="copy"
                class="w-full"
              />
            </div>
            <div>
              <p class="text-[gray] text-[8px] text-center w-[28px] ml-1">
                Format
              </p>
            </div>
          </div>
        </div>
        <div class="ml-2">
          <div class="flex items-center">
            <div class="w-[20px]">
              <img
                src="../assets/images/column.png"
                alt="copy"
                class="w-full"
              />
            </div>
            <div>
              <p class="text-[gray] text-[8px] w-full max-w-full md:w-[62px] ml-1">Merge Columns</p>
            </div>
          </div>
          <div class="flex items-center mt-2">
            <div class="w-[20px]">
              <img
                src="../assets/images/document-download.png"
                alt="copy"
                class="w-full"
              />
            </div>
            <div>
              <p class="text-[gray] text-[8px] w-full max-w-full md:w-[29px] ml-1">Extract</p>
            </div>
            <div class="w-3">
              <img
                src="../assets/images/down-arrow.png"
                alt="seacrh icon"
                class="w-full"
              />
            </div>
          </div>
          <div class="flex items-center mt-2">
            <div class="w-[20px]">
              <img
                src="../assets/images/parsing.png"
                alt="copy"
                class="w-full"
              />
            </div>
            <div>
              <p class="text-[gray] text-[8px] w-[22px] ml-1">Parse</p>
            </div>
            <div class="w-3">
              <img
                src="../assets/images/down-arrow.png"
                alt="seacrh icon"
                class="w-full"
              />
            </div>
          </div>
        </div>
      </div>
      <div class="bg-[#80808053] ml-2 w-[1px] h-[60px]"></div>
      <div class="ml-3 flex items-center">
        <div>
          <div class="mt-2 w-8 flex flex-col justify-center items-center">
            <div class="w-[17px]">
              <img src="../assets/images/file.png" alt="copy" class="w-full" />
            </div>
            <div>
              <p class="text-[gray] text-[8px] text-center w-full max-w-full md:w-[21px]">
                Keep Rows
              </p>
            </div>
          </div>
        </div>
        <div class="ml-2">
          <div class="mt-2 w-8 flex flex-col justify-center items-center">
            <div class="w-[17px]">
              <img src="../assets/images/file.png" alt="copy" class="w-full" />
            </div>
            <div>
              <p class="text-[gray] text-[8px] text-center w-full max-w-full md:w-[39px]">
                Remove Rows
              </p>
            </div>
          </div>
        </div>
      </div>
      <div class="bg-[#80808053] ml-2 w-[1px] h-[60px]"></div>

      <div class="ml-3 flex items-center">
        <div class="ml-2">
          <div class="mt-2 w-8 flex flex-col justify-center items-center">
            <div class="w-[20px]">
              <img src="../assets/images/file.png" alt="copy" class="w-full" />
            </div>
            <div>
              <p class="text-[gray] text-[8px] text-center">Sort by</p>
            </div>
          </div>
        </div>
      </div>
      <div class="bg-[#80808053] ml-2 w-[1px] h-[60px]"></div>

      <div class="ml-3 flex items-center">
        <div>
          <div class="mt-2 w-8 flex flex-col justify-center items-center">
            <div class="w-[20px]">
              <img
                src="../assets/images/columns.png"
                alt="copy"
                class="w-full"
              />
            </div>
            <div>
              <p class="text-[gray] text-[8px] text-center">Statistic</p>
            </div>
            <div class="w-4">
              <img
                src="../assets/images/down-arrow.png"
                alt="seacrh icon"
                class="w-full"
              />
            </div>
          </div>
        </div>
        <div class="ml-2">
          <div class="mt-2 w-8 flex flex-col justify-center items-center">
            <div class="w-[20px]">
              <img
                src="../assets/images/columns.png"
                alt="copy"
                class="w-full"
              />
            </div>
            <div>
              <p class="text-[gray] text-[8px] text-center">Scientific</p>
            </div>
            <div class="w-4">
              <img
                src="../assets/images/down-arrow.png"
                alt="seacrh icon"
                class="w-full"
              />
            </div>
          </div>
        </div>
        <div class="ml-2">
          <div class="mt-2 w-8 flex flex-col justify-center items-center">
            <div class="w-[20px]">
              <img
                src="../assets/images/columns.png"
                alt="copy"
                class="w-full"
              />
            </div>
            <div>
              <p class="text-[gray] text-[8px] text-center">Standard</p>
            </div>
            <div class="w-4">
              <img
                src="../assets/images/down-arrow.png"
                alt="seacrh icon"
                class="w-full"
              />
            </div>
          </div>
        </div>
        <div class="ml-2">
          <div class="flex items-center">
            <div class="w-[20px]">
              <img
                src="../assets/images/pyramid.png"
                alt="copy"
                class="w-full"
              />
            </div>
            <div>
              <p class="text-[gray] text-[8px] w-[60px] ml-1">Trigonometry</p>
            </div>
            <div class="w-4">
              <img
                src="../assets/images/down-arrow.png"
                alt="seacrh icon"
                class="w-full"
              />
            </div>
          </div>
          <div class="flex items-center mt-2">
            <div class="w-[20px]">
              <img
                src="../assets/images/hula-hoop.png"
                alt="copy"
                class="w-full"
              />
            </div>
            <div>
              <p class="text-[gray] text-[8px] ml-1">Rounding</p>
            </div>
          </div>
          <div class="flex items-center mt-2">
            <div class="w-[17px]">
              <img src="../assets/images/info.png" alt="copy" class="w-full" />
            </div>
            <div>
              <p class="text-[gray] text-[8px] w-[37px] ml-1">Information</p>
            </div>
          </div>
        </div>
      </div>
      <div class="bg-[#80808053] ml-2 w-[1px] h-[60px]"></div>

      <div class="ml-3 flex items-center">
        <div>
          <div class="mt-2 w-8 flex flex-col justify-center items-center">
            <div class="w-[20px]">
              <img
                src="../assets/images/calendar.png"
                alt="copy"
                class="w-full"
              />
            </div>
            <div>
              <p class="text-[gray] text-[8px] text-center">Date</p>
            </div>
            <div class="w-4">
              <img
                src="../assets/images/down-arrow.png"
                alt="seacrh icon"
                class="w-full"
              />
            </div>
          </div>
        </div>
        <div class="ml-2">
          <div class="mt-2 w-8 flex flex-col justify-center items-center">
            <div class="w-[20px]">
              <img
                src="../assets/images/back-in-time.png"
                alt="copy"
                class="w-full"
              />
            </div>
            <div>
              <p class="text-[gray] text-[8px] text-center">Time</p>
            </div>
            <div class="w-4">
              <img
                src="../assets/images/down-arrow.png"
                alt="seacrh icon"
                class="w-full"
              />
            </div>
          </div>
        </div>
        <div class="ml-2">
          <div class="mt-2 w-8 flex flex-col justify-center items-center">
            <div class="w-[20px]">
              <img src="../assets/images/event.png" alt="copy" class="w-full" />
            </div>
            <div>
              <p class="text-[gray] text-[8px] text-center">Duration</p>
            </div>
            <div class="w-4">
              <img
                src="../assets/images/down-arrow.png"
                alt="seacrh icon"
                class="w-full"
              />
            </div>
          </div>
        </div>
      </div>
      <div class="bg-[#80808053] ml-2 w-[1px] h-[60px]"></div>

      <div class="ml-3 flex items-center">
        <div>
          <div class="mt-2 w-8 flex flex-col justify-center items-center">
            <div class="w-[20px]">
              <img
                src="../assets/images/letter-r.png"
                alt="copy"
                class="w-full"
              />
            </div>
            <div>
              <p class="text-[gray] text-[8px] text-center w-full max-w-fll md:w-[24px]">
                Run R Script
              </p>
            </div>
          </div>
        </div>
        <div class="ml-2">
          <div class="mt-2 w-8 flex flex-col justify-center items-center">
            <div class="w-[20px]">
              <img src="../assets/images/py.png" alt="copy" class="w-full" />
            </div>
            <div>
              <p class="text-[gray] text-[8px] text-center w-full max-w-full md:w-[45px] ml-1">
                Run Python Script
              </p>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>
<style scoped>
.scroll-bar {
  scrollbar-width: none;
}

.scroll-bar::-webkit-scrollbar {
  display: none;
}
</style>