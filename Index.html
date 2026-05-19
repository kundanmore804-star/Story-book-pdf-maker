import { useState, useRef, useEffect } from "react"
import jsPDF from "jspdf"

export default function StorybookPDFMaker() {
  const [pages, setPages] = useState([])
  const [cover, setCover] = useState(null)
  const [backCover, setBackCover] = useState(null)
  const [darkMode, setDarkMode] = useState(false)
  const [exporting, setExporting] = useState(false)
  const [exportProgress, setExportProgress] = useState(0)
  const [exportSize, setExportSize] = useState("storybook")
  const [online, setOnline] = useState(true)
  const fileInputRef = useRef(null)

  const handlePagesUpload = (e) => {
    const files = Array.from(e.target.files)

    files.sort((a, b) => a.name.localeCompare(b.name))

    const imageUrls = files.map((file) => ({
      url: URL.createObjectURL(file),
      name: file.name,
    }))

    setPages(imageUrls)
  }

  const handleCoverUpload = (e) => {
    const file = e.target.files[0]
    if (file) {
      setCover(URL.createObjectURL(file))
    }
  }

  const handleBackCoverUpload = (e) => {
    const file = e.target.files[0]
    if (file) {
      setBackCover(URL.createObjectURL(file))
    }
  }

  const exportPDF = async () => {
    setExporting(true)
    setExportProgress(0)

    let width = 1080
    let height = 1440

    if (exportSize === "square") {
      width = 1080
      height = 1080
    }

    if (exportSize === "a4") {
      width = 1240
      height = 1754
    }

    if (exportSize === "letter") {
      width = 1275
      height = 1650
    }

    if (exportSize === "kindle") {
      width = 1600
      height = 2560
    }

    const pdf = new jsPDF({
      orientation: "portrait",
      unit: "px",
      format: [width, height],
    })

    const allPages = []

    if (cover) allPages.push(cover)

    pages.forEach((page) => {
      allPages.push(page.url)
    })

    if (backCover) allPages.push(backCover)

    for (let i = 0; i < allPages.length; i++) {
      if (i !== 0) {
        pdf.addPage([width, height], "portrait")
      }

      pdf.addImage(allPages[i], "JPEG", 0, 0, width, height)

      setExportProgress(Math.round(((i + 1) / allPages.length) * 100))
    }

    pdf.save(`storybook-${exportSize}.pdf`)

    setExporting(false)
  }

  useEffect(() => {
    const goOnline = () => setOnline(true)
    const goOffline = () => setOnline(false)

    window.addEventListener("online", goOnline)
    window.addEventListener("offline", goOffline)

    if (!online) {
    return (
      <div className="min-h-screen flex items-center justify-center bg-black text-white text-3xl font-bold">
        No Internet Connection
      </div>
    )
  }

  return () => {
      window.removeEventListener("online", goOnline)
      window.removeEventListener("offline", goOffline)
    }
  }, [])

  return (
    <div className={`${darkMode ? "bg-black text-white" : "bg-neutral-100 text-black"} min-h-screen p-8 flex items-center justify-center`}>
      <div className={`${darkMode ? "bg-neutral-900" : "bg-white"} rounded-3xl shadow-2xl p-8 max-w-5xl w-full`}>
        <h1 className="text-4xl font-bold mb-4 text-center">
          Storybook PDF Maker
        </h1>

        <div className="flex justify-between items-center mb-6 flex-wrap gap-4">
          <p className="text-center flex-1">
            Upload your ready-made pages and export a real-book style PDF.
          </p>

          <button
            onClick={() => setDarkMode(!darkMode)}
            className="bg-black text-white px-4 py-2 rounded-xl"
          >
            Dark Mode
          </button>
        </div>

        <div className="grid grid-cols-2 md:grid-cols-4 gap-3 mb-6">
          <button className="bg-neutral-200 text-black rounded-xl p-3">PDF Preview</button>
          <button className="bg-neutral-200 text-black rounded-xl p-3">Share PDF</button>
          <button className="bg-neutral-200 text-black rounded-xl p-3">Rate App</button>
          <button className="bg-neutral-200 text-black rounded-xl p-3">Feedback</button>
        </div>

        <div className="mb-8">
          <label className="block font-semibold mb-2">Export Size</label>

          <select
            value={exportSize}
            onChange={(e) => setExportSize(e.target.value)}
            className="w-full border rounded-xl p-3 text-black"
          >
            <option value="storybook">Storybook (1080×1440)</option>
            <option value="square">Square (1:1)</option>
            <option value="a4">A4 Size</option>
            <option value="letter">Letter Size</option>
            <option value="kindle">Kindle Size</option>
            <option value="etsy">Etsy Printable Size</option>
            <option value="original">Original Image Size</option>
          </select>
        </div>

        <p className="text-gray-600 text-center mb-8">
          Upload your ready-made pages and export a real-book style PDF.
        </p>

        <div className="border-2 border-dashed border-gray-300 rounded-2xl p-10 text-center mb-6">
          <p className="text-lg font-medium mb-2">Upload Story Pages</p>

          <input
            type="file"
            multiple
            accept="image/*"
            onChange={handlePagesUpload}
            className="block mx-auto"
          />
        </div>

        <div className="grid grid-cols-2 gap-6 mb-8">
          <div className="bg-neutral-50 rounded-2xl p-4 border text-center">
            <p className="font-semibold mb-3">Add Cover Page</p>

            <input
              type="file"
              accept="image/*"
              onChange={handleCoverUpload}
              className="block mx-auto"
            />
          </div>

          <div className="bg-neutral-50 rounded-2xl p-4 border text-center">
            <p className="font-semibold mb-3">Add Back Cover</p>

            <input
              type="file"
              accept="image/*"
              onChange={handleBackCoverUpload}
              className="block mx-auto"
            />
          </div>
        </div>

        <div className="bg-neutral-50 border rounded-2xl p-6 mb-8">
          <div className="flex flex-wrap gap-3 mb-6">
            <button
              onClick={() => setPages([...pages].reverse())}
              className="bg-orange-500 hover:bg-orange-600 text-white px-4 py-2 rounded-xl font-medium"
            >
              Reverse Pages
            </button>

            <button
              onClick={() => {
                setPages([])
                setCover(null)
                setBackCover(null)
              }}
              className="bg-red-500 hover:bg-red-600 text-white px-4 py-2 rounded-xl font-medium"
            >
              Clear Book
            </button>
          </div>
          <h2 className="text-xl font-bold mb-4">Book Preview</h2>

          <div className="grid grid-cols-2 md:grid-cols-3 gap-4">
            {cover && (
              <div>
                <p className="text-sm font-semibold mb-2">Cover</p>
                <img
                  src={cover}
                  alt="Cover"
                  className="rounded-xl border"
                />

                <div className="flex gap-2 mt-2 flex-wrap">
                  <button
                    onClick={() => {
                      const duplicated = [...pages]
                      duplicated.splice(index, 0, page)
                      setPages(duplicated)
                    }}
                    className="bg-blue-500 text-white px-2 py-1 rounded-lg text-xs"
                  >
                    Duplicate
                  </button>

                  <button
                    onClick={() => {
                      const reordered = [...pages]
                      if (index > 0) {
                        ;[reordered[index], reordered[index - 1]] = [
                          reordered[index - 1],
                          reordered[index],
                        ]
                        setPages(reordered)
                      }
                    }}
                    className="bg-purple-500 text-white px-2 py-1 rounded-lg text-xs"
                  >
                    Move Up
                  </button>
                </div>
              </div>
            )}

            {pages.map((page, index) => (
              <div key={index}>
                <p className="text-sm font-semibold mb-2">
                  Page {index + 1} • {page.name}
                </p>

                <img
                  src={page.url}
                  alt={`Page ${index + 1}`}
                  className="rounded-xl border"
                />

                <div className="flex gap-2 mt-2 flex-wrap">
                  <button
                    onClick={() => {
                      const duplicated = [...pages]
                      duplicated.splice(index, 0, page)
                      setPages(duplicated)
                    }}
                    className="bg-blue-500 text-white px-2 py-1 rounded-lg text-xs"
                  >
                    Duplicate
                  </button>

                  <button
                    onClick={() => {
                      const reordered = [...pages]
                      if (index > 0) {
                        ;[reordered[index], reordered[index - 1]] = [
                          reordered[index - 1],
                          reordered[index],
                        ]
                        setPages(reordered)
                      }
                    }}
                    className="bg-purple-500 text-white px-2 py-1 rounded-lg text-xs"
                  >
                    Move Up
                  </button>
                </div>
              </div>
            ))}

            {backCover && (
              <div>
                <p className="text-sm font-semibold mb-2">Back Cover</p>
                <img
                  src={backCover}
                  alt="Back Cover"
                  className="rounded-xl border"
                />

                <div className="flex gap-2 mt-2 flex-wrap">
                  <button
                    onClick={() => {
                      const duplicated = [...pages]
                      duplicated.splice(index, 0, page)
                      setPages(duplicated)
                    }}
                    className="bg-blue-500 text-white px-2 py-1 rounded-lg text-xs"
                  >
                    Duplicate
                  </button>

                  <button
                    onClick={() => {
                      const reordered = [...pages]
                      if (index > 0) {
                        ;[reordered[index], reordered[index - 1]] = [
                          reordered[index - 1],
                          reordered[index],
                        ]
                        setPages(reordered)
                      }
                    }}
                    className="bg-purple-500 text-white px-2 py-1 rounded-lg text-xs"
                  >
                    Move Up
                  </button>
                </div>
              </div>
            )}
          </div>
        </div>

        <button
          onClick={exportPDF}
          className="w-full bg-black hover:bg-neutral-800 text-white py-4 rounded-2xl text-lg font-bold transition-all"
        >
          {exporting ? `Exporting ${exportProgress}%` : "Export Real Book PDF"}
        </button>
      </div>
    </div>
  )
}
