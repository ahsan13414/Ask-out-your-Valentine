import { useState } from "react"; import { motion } from "framer-motion"; import { Button } from "@/components/ui/button";

export default function LoveTrap() { const [noClicks, setNoClicks] = useState(0); const [showFinal, setShowFinal] = useState(false);

const yesButtonScale = 1 + noClicks * 0.3; const questions = [ "Do you love me?", "Are you sure you don't love me?", "Really...? Not even a little bit?", "Come on, say yes!", "Just click yes, my love...", "You can't escape the YES!" ]; const currentQuestion = questions[Math.min(noClicks, questions.length - 1)];

return ( <div className="min-h-screen flex items-center justify-center bg-pink-100 p-4"> {!showFinal ? ( <motion.div className="text-center bg-white p-6 rounded-2xl shadow-xl max-w-md w-full" initial={{ opacity: 0 }} animate={{ opacity: 1 }} > <h1 className="text-2xl font-bold text-pink-600 mb-6"> {currentQuestion} </h1> <div className="flex justify-center gap-4"> <motion.button className="bg-pink-500 text-white px-6 py-2 rounded-full text-lg" style={{ transform: scale(${yesButtonScale}) }} onClick={() => setShowFinal(true)} whileTap={{ scale: 0.95 }} > Yes </motion.button> <motion.button className="bg-gray-300 px-6 py-2 rounded-full text-lg" onClick={() => setNoClicks(noClicks + 1)} whileTap={{ scale: 0.95 }} > No </motion.button> </div> </motion.div> ) : ( <motion.div className="text-center bg-white p-6 rounded-2xl shadow-xl max-w-lg w-full" initial={{ scale: 0 }} animate={{ scale: 1 }} transition={{ type: "spring", stiffness: 200 }} > <h2 className="text-2xl font-bold text-pink-600 mb-4"> I love you more, my love! </h2> <img
src="/mnt/data/file-1pYj8FoVg1kLwQCAb7BNWU"
alt="Us Together"
className="w-48 mx-auto rounded-2xl border-4 border-pink-300 mb-4"
/> <p className="text-lg text-pink-700 font-semibold"> You are my world. You are mine forever, Lava Cake. </p> </motion.div> )} </div> ); }


